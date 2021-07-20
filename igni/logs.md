---
layout: default
toc: true
footer: (c) Copyright <a href="https://ids.company">ids.company</a> 2021.
---
# Logs

igni has advanced logs, but that comes with a compromise - they're a bit harder to setup in text chat (on our dashboard with UI, it will be much simpler).

## Adding channel to logs

To add channel to logs, simply call `logs add` or `logs set` with channel name, like
```
!logs add #logs
```

## Editing rules for logs

To edit rules, call `logs alter` with channel name and rule alterations.

### List of rules

Aztec uses minecraft-permissions-like rules for logs. A list of all rules can be seen here:

 * `*` - Wildcard, any event (default)
 * `*.*` - Alias to `*`
 * `user.*` - Any user related event
 * `channel.*` - Any channel related event (messages aren't part of it)
 * `category.*` - Any category related event (category create/update/delete)
 * `message.*` - Message related event (excluding new messages)
 * `guild.*` - Server related events (rename, ban, region change etc)
 * `roles.*` - Roles related events
 * `config.*` - Bot config related events
 * `emoji.*` - Emoji create/rename/delete
 * `invite.*` - Invite related events
 
 * `user.join` - When user joins the server
 * `user.leave` - When user leaves the serevr
 * `user.update` - User update (avatar change, rename etc) [doesn't work]
 * `user.presenceUpdate` - On user presence change. Can be enabled only by bot owner.
 
 * `channel.create` - When new channel is created
 * `channel.delete` - When channel is deleted
 * `channel.pins` - When there's a new pinned message [doesn't work]
 * `channel.update` - When channel is updated (currently excluding permission changes)
 * `channel.name` - When channel is renamed
 
 * `category.create` - When category is created
 * `category.delete` - When category is deleted
 * `category.perms` - When permissions for category are changed [doesn't work]
 * `category.name` - When category is renamed
 
 * `guild.update` - When guild is updated (excluding permission changes)
 * `guild.boost` - When premium user boosts guild (bot boosting, not discord boost)
 * `guild.ban` - When user gets banned
 * `guild.removeBan` - When user gets unbanned
 * `guild.integration` - When there's new integration [doesn't work]
 * `guild.kick` - When user gets kicked
 * `guild.warn` - When user gets warned **using igni**
 * `guild.webhook` - When guild webhook settings changes [doesn't work]
 
 * `roles.create` - When role is created
 * `roles.update` - When role is updated
 
 * `message.withLink` - When a message with link is posted [doesn't work, might be removed later]
 * `message.withInvite` - When a message with invite to server is posted [doesn't work, might be removed later]
 * `message.edit` - When message is edited
 * `message.delete` - When message is deleted
 * `message.purge` - When messages are purged (mass deleted)
 
 * `emoji.create` - When emoji is created [doesn't work]
 * `emoji.delete` - When emoji is deleted [doesn't work]
 * `emoji.update` - When emoji is updated [doesn't work]
 
 * `invite.create` - When invite is created
 * `invite.delete` - When invite is deleted
 
 ### Alterations
 
 Channels are updated using `alterations` which is specified by a single character before rule - either `-` (remove), `+` (add) or `!` (toggle, invert).
 
 You can put as many alterations after each other as you want.
 
 **Example**
 
 *The following will log every message edit*
 ```
 !logs alter #logs -* +message.edit
 ```
 *Note that you need to remove wildcard first before other rules take effect*
 
 ## Removing channel from logs
 
 You can remove logs channel using `remove` subcommand:
 
 ```
 !logs remove #logs
 ```