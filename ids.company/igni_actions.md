---
layout: default
toc: true
footer: (c) <a href="https://ids.company">ids.company</a> 2021
---
# igni actions proposal

Actions are a way for developers to extend igni on a per-server basis. Actions:
* are part of modules (each action must belong to a module)
* can have settings (for member, user, or server), settings may or may not be editable from the website (as defined by [module.json](#module.json))
* can have a service, which consists of at least one event listener and/or intervals
* must have at least one command

## SDK

Modules and actions are to be developed using our SDK. The SDK consists of Commando (the main library for commands and services, edited to serve our needs) and the command-line utility (imm).

### Commando

Commando should work nearly identically to [`@iceprod/discord.js-commando`](https://github.com/iceproductions/commando), with its differences being:
* Commands and event handlers MUST await all its promises, as the process may be killed at __any__ time after the function returns.
* Collectors are not to be passed a function directly, instead, you should pass a name of the function __in the same class__.
* There's no guilds property on the client, the only guild available is the one the event originated from.
* Embeds MUST be used when sending direct messages, sending plain text is not supported.
* Footers will be ignored when sending direct messages, instead, the following is used: `via <module name>, <server name>`.
* Direct messages are rate limited to 5 *total* per event run. Edits don't count, deleted messages will still count towards the total (as this state isn't shared).
* New settings function: getSettingsFromModule accepting `module`, `setting` and (optionally) `default` value. Used for getting public settings of other modules. Throws an error if module doesn't exist or if setting is private.
* New method on guild: isModuleInstalled accepting `module` (string).

### IMM (igni module manager)

#### Installation

To install, you can run `npm i -g imm` as administrator (or using `sudo` on Linux) or use the `npx imm setup` command which will also create a bare project to get started with.

#### module.json

Module file is used for setting properties of the module bundle.

Required fields:
* **name** - The code name to be used for the module. It will appear in URLs and can be used to get help. Must be unique in the account. Must be of the following RegEx: `[A-Za-z][0-9a-zA-Z_-]{2,15}`
* **display_name** - The display name of the module, will be used for UI (in help, in module listing...). Can be any character (must be a valid text to get verified, emoji must not be used in public modules.)
* **lang** - Language to use, currently only supported is `node`.

Optional fields
* **team** - Not used, reserved for future use.
* **version** - The version of language, defaults to `latest`. Semantic versioning accepted.
* **entry** - The entry file to start, defaults to the default entry file of selected language.
* **settings** - An array of objects with `name`, `type`, `description` and optionally `default`.
* **public** - Array of settings that are readable by other modules.

##### Module settings

* `name` - must be a valid settings name, will directly be saved into guild settings as-is. Must pass the following RegEx: `[a-z][a-z0-9-_]{2,15}`
* `type` - must be one of the following (case insensitive): `string`, `text` (multiline), `switch` (alias `bool` and `boolean`; results in boolean), `integer`, `float` (alias `number`), `range` (alias `integer-range`), `float-range` and `date`.
* `from` - Optionally, only allowed for number types. Specifies the minimum number. Must be valid to that type.
* `to` - Same as previous.
* `oneOf` - Optional array of possible values, if set `from`, and `to` are ignored. Not usable for `switch` and `range`s.
* `default` - Specifies the default value, makes it optional (when a required setting is not filed, the module will not be active). As long as it's set, it makes the setting optional (you can use `null` as the default variable too).

Ranges are returned in the format of an array with 2 elements. Dates are returned as a stringified Date object (`(new Date).toString()`).

###### Example

```json
{
    "name": "example-module",
    "display_name": "Example module",
    "lang": "node"
}
```

### Commands

#### `setup`

Setups the project from start (interactively). Creates a `package.json` for npm, installs the required dependencies, creates `module.json`, and attempts (or guides you how) to install `imm` globally. Can be used directly from `npx`.

#### `init`

Will initialize the `module.json` file with specified options. `-y` (alias `--yes`) flag to use default values.

#### `publish`

Uploads the module to igni. Requires user to be logged in.

#### `login` (alias `connect`)

Creates a link to login via discord.

#### `logout` (alias `disconnect`)

Logs out the current user.

#### `run` (alias `test`)

Runs the test bot. Uses token from `DISCORD_TOKEN` environmental variable (also uses `.env` file), `token.txt` or `--token` (`--token <token>`) flag.
No settings are preserved during restarts. Uses lots of debugging statements, so performance may be lower than on igni.

### Supported languages

#### Node

The latest long-term support (LTS) release supported, backward compatibility is on the best effort basis. Entry file is `index.js`.

##### Getting started with node

To start with node, run `npx imm setup node`. It will create a folder with all the required files while installing imm globally (if needed).

A sample `index.js` file to use:
```js
const igni = require("igni");

igni
    .registerCommandsIn("cmd")
    .registerDefaultTypes()
    .registerServicesIn("services");
```

A sample folder structure:
```plaintext
project/
    cmd/
    services/
    index.js
    module.json
    package.json
```

Command folder (`cmd`) expects to directly have files (folder structure is flattened, so you can group commands).
Service folder (`services`) expects to directly have files or grouped files (Grouped services can be managed per group or per service). Further levels are flattened.

> **optional:** Use eslint with `require-await` rule. It's recommended as it's needed for getting verified (there can't be any side-effect promise functions).

### .immignore file

`.immignore` file is used for ignoring files to be uploaded. Its format is identical to `.gitignore` and `.npmignore`.

IMM ignores by default the folder `node_modules` and the file `package-lock.json`.

### Maximum size

The file system allows 32MB of space (including dependencies). Trying to use more will result in an error and the module failing to start. Verification increases the limit (per case).

## Modules

Modules are a bundle of actions. Its properties are defined by [module.json](#module.json) in the top directory of the module.

Global variables will not work.

### Commands

Commands are defined similarly to normal commando commands. Nearly any command working in commando will work in igni actions.

For collectors, you need to refactor the code to be stateless (the process may get restarted before the collector handler is started) and to use a method in the command class instead of directly passing a callback function.
Await reactions/messages will not work (and are not defined). Filters are needed to be passed as method names too. Collectors now accept a third parameter, ID which is used to share state id. Must be short, you can usually use message ID.
ID must be a string or number (`toString` method will be used).

```js
module.exports = class Command extends commando.Command {
    // ... constructor
    run(msg) {
        var collector = this.createMessageCollector(
            msg.channel,
            "collectFilter",
            {
                time: 15000,
                errors: ["time"]
            }
        );
        collector.collect("collect", msg.id);
        collector.error("collectError", msg.channel.id);
        return msg.reply("Reply with any message");
    }
    
    async collectError(error, id) {
        var channel = await client.channels.fetch(id);
        channel.reply("No message was sent");
    }
    
    collectFilter(msg, id) {
        return true; // accept any message
    }
    
    async collect(msg, id) {
        var original = await msg.channel.messages.fetch(id);
        msg.reply("You replied with " + msg.content + " to `" + original.content + "`.");
    }
}
```

### Services

Services are a set of event handlers and intervals. Most events will be used, except for those that cannot be linked to guilds (thus the action runner can't see which actions to run).

Intervals have a requirement of being static (you can't change the interval length or add intervals while the action is running, only in the service definition.). Services must have a name where the same rules as for command names apply (must be unique across services).

For message event, do NOT use it if you can write a RegEx for it - it will be much faster to create a command with a pattern set (e.g. to create `owo` counter, create a command where its pattern is `\bowo\b`.).
It will also use less CPU time, thus actions may be cheaper. Event handlers now also allow third parameter - options, which may specify a rule for the event. Again, it's to make things as fast as possible, so we want to run the handler the least possible times.

Both intervals and event handlers require all promises to be awaited (in the same way as commands).

```js
module.exports = class Service extends commando.Service {
    name = "test-service";
    load() {
        this.on("guildMemberAdd", "memberAdd", {
            settings: {
                guild: {
                    "join-channel": true // requires join-channel to be set and non-falsy. Use null to allow falsy values. Use false to require the setting NOT to be set.
                }
            }
        })
    }
    
    async memberAdd(member) {
        var channelID = await member.guild.settings.get("join-channel");
        try {
            var channel = await member.guild.channels.fetch(channelID);
        } catch(e) { // if channel gets deleted, fail silently
            await member.guild.sendNotification({ // send notification to guild administrators
                type: "warning",
                content: "Test service cannot find channel " + channelID
            });
            await member.guild.settings.set("join-channel"); // setting to undefined removes the setting, thus disabling this service
            return;
        }
        try {
            await channel.send(`${member.displayName} joined the server!`);
        } catch(e) {
            await member.guild.sendNotification({
                type: "warning",
                content: "Test service cannot send messages to channel " + channel.name
            });
            await member.guild.settings.set("join-channel");
        }
    }
}
```

#### Alternate services format idea

Have services use callbacks (like currently in commando) and instead of callback names just use the service name and find it in a map (then each map would have an array of callbacks to call).

#### Event rules

Event rules are an object that's used as 3rd parameter in event handlers. It's properties are `settings`, containing object with `guild`, `member` and/or `user` that each contain setting name mapped to `true` (set and non-falsy), `null` (set) or `false` (not set).

Another property is `clientPermissions`, which is an array of permissions that are needed for the handler to be usable and `userPermissions`, ignored by events where action runner can't get a user, for an array of permissions a user needs to have.

It also haves a property `manageable`, which specified if the dashboard should allow enabling/disabling the event handler. This requires another property, `name` to be set (display name for event handler), and allowing
optional property `description`.

**Example:**
```js
{
    settings: {
        member: {
            allowLevelup: true
        }
    },
    clientPermissions: ["EMBED_LINKS"],
    manageable: true,
    name: "Level up messages",
    description: "Sends a level up message to specified channel whenever a user levels up."
}
```


#### Intervals

Intervals need to be at least 30 minutes apart and are NOT guaranteed to be in exact times (action runner may be few seconds to minutes late/too fast or the interval may not be run at all).
You cannot set multiple intervals to the same handler and each service is limited to 2 intervals. The interval handler is run for every guild separately.

They need to be static (intervals cannot change their time once they're defined) and cannot be added on runtime. You can disable intervals using the `disableInterval` method and enable them back by using the `enableInterval` method,
you cannot add new handlers once the service is loaded (you can only use this on the already-enabled intervals). Those methods exist on the client, so you can use them in commands as well (they're saved into `<service name>-interval-<handler name>` setting).

You can check the next scheduled time for an interval by `getInterval` which returns the next `Date` object, representing the time at which the handler should be called.

Intervals allow a 3rd parameter similar to event rules, except `userPermissions`, member settings, and user settings are ignored. Guild settings are moved directly into settings.

```js

module.exports = class Service extends commando.Service {
    name = "test-interval-service";
    load() {
        this.setInterval("bumpNotification", 2 * 60 * 1000, {
            settings: {
                "bump-channel": true
            },
            name: "Bump notification",
            mamageable: true,
            description: "Sends a message every 2 hours to specified channel."
        }); // ran every two hours
    }
    
    async bumpNotification(guild) {
        var channelID = await guild.settings.get("bump-channel");
        try {
            var channel = await guild.channels.fetch(channelID);
        } catch(e) {
            await guild.settings.set("bump-channel");
            return await guild.sendNotification({ // send notification to guild administrators
                type: "warning",
                content: "Test interval service cannot find channel " + channelID
            });
        }
        try {
            await channel.send({
                embed: {
                    title: "Bump",
                    description: "You can use the `bump` command now."
                }
            });
        } catch(e) {
            await guild.settings.set("bump-channel");
            await guild.sendNotification({ // send notification to guild administrators
                type: "warning",
                content: "Test interval service cannot send messages to " + channel.name
            });
        }
    }
}
```

### Getting started

To get started, create a node project with commando, init `imm` and start working on commands and services. To ease this process, you can use `npx imm setup` to guide you on how to set up your project.

## Timeouts

* initial run (loading services and commands) **10 seconds**
* types (validating and parsing arguments) **2 seconds** each, **5 seconds** total
* command run **30 seconds**
* interval **15 seconds**
* event handler **30 seconds**, max 2 simultaneously of the same type, others will be buffered
* collectors **1 minute** (after that, they will be canceled and error callback will be run if `time` is in error array), one per command run simultaneously of the same type (you can have reaction and message collector at the same time)

## Verification

Module verification will be needed for the module to be available publicly on igni. The requirements are as follows:

* No errors - the bot should not ever respond with an error. If the command showing an error is optional, it may not prevent the verification but the command will be disabled.
* Checks permissions - when the bot performs an operation that normally requires permissions, the command should check the user has given permissions (using the `userPermissions` property).
* Timeouts are not exceeded - the timeouts must be fulfilled to be verified, favorably with some time margin. Timeouts may be increased when given a good enough reason.
* No side-effect promises - promises must be awaited (at least in the end before returning using the `await Promise.all` method) before the command/service returns.
* The module accomplishes something - set a goal and fulfill it, don't have just some empty commands.
* Doesn't break any TOS or laws, including copyright. Using a free API (or paid one with a legally obtained token) is fine, scraping sites that explicitly forbid it is not.
* Has a description - this means that the module has a semi-unique name and a description describing most (if not all) of its features and that each command has its own description.
* Name must have readable characters - that's not limited to English (if you're making a module for the Chinese market, you can use Chinese characters) but it doesn't include emojis. Emojis can be in the name, but limit them to two maximum.

## Pricing

Github actions-like pricing might be used, i.e. per-minute pricing for each run. Each server could have a set of minutes for free (might be set on member range so bigger servers would have a bit more free minutes).

Github pricing:
| Plan                  | Disk space (settings space?)   | Minutes  |
| ----                  | ----------------------------   | -------  |
| GitHub Free	        | 500 MB	                     | 2,000    |
| GitHub Pro (4$/month)	| 1 GB   	                     | 3,000    |

## Implementation details

### Initial run

* load all commands and services
* save their metadata into the database (for help, dashboard, and info needed for running)
* exit

### Cold start

When the module is started after some time of inactivity.

The module should listen on the port specified by IGNI_PORT (defaulting to 3000).

* load commands or services based on what's needed first
* run the required services/commands
* load the rest

### Warm start

* run the required services/commands

### Context

In the node context, setTimeout, setInterval, and setImmediate should be undefined. Instead, `awaitTimeout` should return a promise that resolves after *x* ms.

Promises could be proxied so that whenever a promise doesn't return before the command returns, a warning/error would be shown. We could also recommend using the `require-await` eslint rule.

### Communication

Communication should be done by WebSockets. Port TBD.

Types should be similar to API returned (using the `toJSON` method).

#### Nonces

Nonces are optional for requests, in which case the server should respond with the same nonce.

#### Command runs

```json
{
    "type": "commandRun",
    "message": {
        "content": "command-name arg1 arg2",
        ...
    },
    "guild": { ... },
    "member": { ... },
    "author": { ... }
}
```

#### Event runs

Params contain the same fields as in discord.js event handlers.
```json
{
    "type": "...",
    "params": [ ... ]
}
```

#### Settings

Request:
```json
{
    "type": "settings",
    "sub": "guild",
    "nonce": "xxx"
}
```

Data:
```json
{
    "type": "settings",
    "sub": "guild",
    "nonce": "xxx",
    "data": { ... }
}
```

Setting data in request results in updating settings.

#### Fetching objects

Responses should be the same as using default API, using the `toJSON` method.

```json
{
    "type": "channel",
    "id": "287158"
}
{
    "type": "user", // alias member
    "id": "177013"
}
{
    "type": "channels"
}
{
    "type": "members",
    "query": "..."
}
```

#### Registering collector

```json
{
    "type": "collector",
    "sub": "message", // or reaction
    "channel": "287158",
    "options": {
        "time": 15000,
        "errors": ["time"]
    },
    "callbacks": {
        "filter": "command:collectFilter",
        "collect": "command:collect",
        "error": "collect:collectError"
    }
}
```

#### Running callbacks

If the filter passes, the action runner should automatically run the callback while replying.
```json
{
    "type": "collectorError",
    "sub": "command:collectError",
    "id": "123456",
    "error": {
        "reason": "time",
        ...
    }
}
{
    "type": "collectorFilter",
    "sub": "command:collectFilter",
    "callback": "command:collect",
    "id": "123456",
    "message": { ... }
}
```

#### Collector filter reply

Sent to action runner.
```json
{
    "type": "collectorFilterReply",
    "id": "123456",
    "message": "123457", // message id
    "value": true // boolean
}
```

## Revisions

**Rev 1**
* Added `public` optional field to [module.json](#module.json).
* Added functions `getSettingFromModule` and `isModuleInstalled` to [commando](#commando).
* Added `nonce`s to [Communication](#communication).