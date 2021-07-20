---
layout: default
toc: true
footer: (c) Copyright <a href="https://ids.company">ids.company</a> 2021.
---
<!-- This file is used on the bot lists. -->
# Igni

**We highly recommend reading through this description before inviting the bot to see how it works.**

Igni is a universal all-in-one bot. It's the next generation of bots, starting with a unique command handling - if you make a typo, for most commands, you can just edit the command and the bot will update it's reply, even if the previous message didn't start with a correct prefix. That means it's easier as you don't have to type out the entire command, and also less messages in chat so you can stay focused on having a nice conversation rather than typing commands.

## Things to know

* Prefix can have spaces after, so for example `!` will also match `!  `. Make sure to not use `>` as that's how quotes start.
* The bot will ask for arguments, use cancel if you don't want to reply (or wait the default 30s timeout).

## No more pings

Any command that requires a user to be selected can be called without a ping - just type the users name, nickname or tag.

## No more retyping commands

If you missed a required parameter for a command, the bot will just ask for it. Just send the parameter as a message instead of retyping the whole command.

## Many commands

You don't need 20 bots, each doing their own thing. In past, you had to because the universal bots did many things, but most of them poorly. Igni does many things as well, but we focused on one thing at a time so you (the user) have a pleasant experience.

## Aztec user?

Igni is the reincarnation of Aztec. As such, we had done a way to move all your data to igni (we didn't move any data without your consent). Simply use the **aztec** command `deprecated` to get all the steps required to move.

## More to come soon

We didn't stop on the development of the bot! We're still working on features such as web dashboard, custom commands, templates and more. Be sure to join our support server for any news we might have!

## Testing

We have a separate server for testing the bot and talking about it's development. If you want to be more involved, you can join [here](https://discord.gg/EJujSYv).

These features are not stable and/or have known bugs:
* Music playback
* investments

## Temporary features

Some features are still in testing and may **be reset at any time**.
* Tickets - we're currenlty working on a much better ticket system than the current one that will be at *least* on the same level as bots dedicated to tickets (might mean that the tickets created before the change may not be manageable by the bot).
* Ranks - We're experimenting with the values for ranking system, and as such the data may be reset to be more fair.
* Auto reactions - this feature is in public testing, but may be altered to allow for more features which may lead to losing settings (meaning the bot won't react to messages).

## FAQ

| Question | Answer |
| -------- | ------ |
| The bot is sending messages asking me for something. How to stop it? | This is part of the unique command system. When a required argument is missing, the bot will ask. There's a timeout of 30 seconds after last question, so by the team you're reading this the bot already stopped asking. Else, you could've just read what the bot said and responded with the message of "cancel" (without quotes) |
| How to change prefix? | Use the prefix command with an argument of the new prefix. Put it in quotes to force spaces. |
| What's the prefix? | Default prefix is `!`, you can get the one simply by pinging the bot (with nothing else in the message). Pinging the bot is a valid prefix too. |
| Is there a global prefix? | Yes there is, pinging the bot works as a prefix anywhere. |
| How do I disable the unknown command message? | Unknown command is a command too - `unknown-command`. Disable it (using the `disable` command) and the bot will stop replying with unknown command |
| How do I disable specific channels? | You can use the `channels` command to manage which channels are allowed. See `help channels`. |
| How do I manage who can use the bot? | For now, best would be to wait for dashboard. There's a way using `alter-perms` but it's hard to manage in chat and can yield unexpected results. If you enable a role to use a command, it will bypass the permission check. Proceed at your own risk! |
| How do I select which commands/groups can be used? | You can use the `enable` and `disable` commands to do just that. |

# Commands

- [Igni](#igni)
  - [Things to know](#things-to-know)
  - [No more pings](#no-more-pings)
  - [No more retyping commands](#no-more-retyping-commands)
  - [Many commands](#many-commands)
  - [Aztec user?](#aztec-user)
  - [More to come soon](#more-to-come-soon)
  - [Testing](#testing)
  - [Temporary features](#temporary-features)
  - [FAQ](#faq)
- [Commands](#commands)
  - [animals](#animals)
    - [birb](#birb)
    - [cat](#cat)
    - [dog](#dog)
    - [fox](#fox)
    - [kangaroo](#kangaroo)
    - [koala](#koala)
    - [panda](#panda)
    - [racoon](#racoon)
    - [redpanda](#redpanda)
  - [anime](#anime)
    - [awooify](#awooify)
    - [baguette](#baguette)
    - [cry](#cry)
    - [ddlc](#ddlc)
    - [declare](#declare)
    - [drink-coffee](#drink-coffee)
    - [gah](#gah)
    - [hug](#hug)
    - [kanna](#kanna)
    - [kannagen](#kannagen)
    - [kemonomimi](#kemonomimi)
    - [kiss](#kiss)
    - [lick](#lick)
    - [lolice](#lolice)
    - [neko](#neko)
    - [pout](#pout)
    - [quote](#quote)
    - [safebooru](#safebooru)
    - [shrug](#shrug)
    - [sip](#sip)
    - [slap](#slap)
    - [smug](#smug)
    - [sofurry](#sofurry)
    - [waifu](#waifu)
  - [dev](#dev)
    - [apm](#apm)
    - [caniuse](#caniuse)
    - [chart](#chart)
    - [code](#code)
    - [color](#color)
    - [djs](#djs)
    - [dstatus](#dstatus)
    - [embed](#embed)
    - [emotes](#emotes)
    - [format](#format)
    - [is-emoji](#is-emoji)
    - [logme](#logme)
    - [lolcode](#lolcode)
    - [npm](#npm)
    - [php](#php)
    - [pip](#pip)
    - [request](#request)
    - [uptime](#uptime)
  - [economy](#economy)
    - [balance](#balance)
    - [beg](#beg)
    - [invest](#invest)
    - [investments](#investments)
    - [leaderboard](#leaderboard)
    - [mine](#mine)
    - [pay](#pay)
    - [rank](#rank)
    - [rich](#rich)
    - [search-internet](#search-internet)
    - [top-counters](#top-counters)
    - [top-inviters](#top-inviters)
    - [withdraw-investment](#withdraw-investment)
    - [xp](#xp)
  - [essentials](#essentials)
    - [achievements](#achievements)
    - [afk](#afk)
    - [avatar](#avatar)
    - [close-tunnel](#close-tunnel)
    - [convert](#convert)
    - [count](#count)
    - [covid](#covid)
    - [fact](#fact)
    - [flags](#flags)
    - [invite](#invite)
    - [last-ping](#last-ping)
    - [math](#math)
    - [oldest](#oldest)
    - [random-avatar](#random-avatar)
    - [randomcolor](#randomcolor)
    - [reddit](#reddit)
    - [reddituser](#reddituser)
    - [request-tunnel](#request-tunnel)
    - [stats](#stats)
    - [subinfo](#subinfo)
    - [translate](#translate)
    - [voted](#voted)
    - [wttr](#wttr)
  - [fun](#fun)
    - [ascii](#ascii)
    - [catfact](#catfact)
    - [clap](#clap)
    - [coinflip](#coinflip)
    - [cool](#cool)
    - [cow](#cow)
    - [dab](#dab)
    - [dadjoke](#dadjoke)
    - [impostor](#impostor)
    - [joke](#joke)
    - [kill](#kill)
    - [leetify](#leetify)
    - [lenny](#lenny)
    - [reversetext](#reversetext)
    - [rps](#rps)
    - [say](#say)
    - [snipe](#snipe)
    - [snipelist](#snipelist)
    - [spoiler](#spoiler)
    - [subscript](#subscript)
    - [superscript](#superscript)
    - [throw](#throw)
    - [topic](#topic)
    - [vaporwave](#vaporwave)
  - [games](#games)
    - [apexuser](#apexuser)
    - [mastermind](#mastermind)
    - [mc](#mc)
    - [osuuser](#osuuser)
    - [pokedex](#pokedex)
    - [skin](#skin)
    - [trivia](#trivia)
    - [wouldyourather](#wouldyourather)
  - [giveaway](#giveaway)
    - [end-giveaway](#end-giveaway)
    - [reroll-giveaway](#reroll-giveaway)
    - [start-giveaway](#start-giveaway)
  - [image](#image)
    - [facepalm](#facepalm)
    - [pat](#pat)
    - [wink](#wink)
    - [achievement](#achievement)
    - [blurpify](#blurpify)
    - [captcha](#captcha)
    - [changemymind](#changemymind)
    - [clyde](#clyde)
    - [coffee](#coffee)
    - [deepfry](#deepfry)
    - [endtask](#endtask)
    - [fone](#fone)
    - [food](#food)
    - [gay](#gay)
    - [glass](#glass)
    - [iphonex](#iphonex)
    - [jpeg](#jpeg)
    - [lookingback](#lookingback)
    - [magik](#magik)
    - [makeameme](#makeameme)
    - [phcomment](#phcomment)
    - [qr](#qr)
    - [salty](#salty)
    - [sauce](#sauce)
    - [stickbug](#stickbug)
    - [tenor](#tenor)
    - [threats](#threats)
    - [trap](#trap)
    - [trash](#trash)
    - [triggered](#triggered)
    - [trumptweet](#trumptweet)
    - [wasted](#wasted)
    - [whowouldwin](#whowouldwin)
    - [xkcd](#xkcd)
    - [ytcomment](#ytcomment)
  - [mod](#mod)
    - [alias](#alias)
    - [alter-automod](#alter-automod)
    - [alter-perms](#alter-perms)
    - [announce](#announce)
    - [auto-react](#auto-react)
    - [automod](#automod)
    - [ban](#ban)
    - [case](#case)
    - [channels](#channels)
    - [clear-perms](#clear-perms)
    - [clearsettings](#clearsettings)
    - [counting](#counting)
    - [edit-embed](#edit-embed)
    - [history](#history)
    - [import](#import)
    - [info](#info)
    - [kick](#kick)
    - [lock](#lock)
    - [logs](#logs)
    - [media-lock](#media-lock)
    - [media-locks](#media-locks)
    - [mute](#mute)
    - [perms](#perms)
    - [poll](#poll)
    - [purge](#purge)
    - [random-member](#random-member)
    - [reaction-roles](#reaction-roles)
    - [reason](#reason)
    - [removewarn](#removewarn)
    - [role](#role)
    - [rrm](#rrm)
    - [settings](#settings)
    - [softban](#softban)
    - [stats-channels](#stats-channels)
    - [unban](#unban)
    - [unlock](#unlock)
    - [unmute](#unmute)
    - [warn](#warn)
    - [welcomechannel](#welcomechannel)
  - [music](#music)
    - [clear-queue](#clear-queue)
    - [jump](#jump)
    - [leave](#leave)
    - [loop](#loop)
    - [move](#move)
    - [now](#now)
    - [pause](#pause)
    - [play](#play)
    - [queue](#queue)
    - [remove](#remove)
    - [resume](#resume)
    - [save-song](#save-song)
    - [seek](#seek)
    - [shuffle](#shuffle)
    - [skip](#skip)
    - [stop](#stop)
    - [volume](#volume)
  - [scircles](#scircles)
    - [invited](#invited)
    - [profile](#profile)
    - [scircles-description](#scircles-description)
    - [set-timezone](#set-timezone)
    - [timezones](#timezones)
    - [tz-list](#tz-list)
  - [search](#search)
    - [bang](#bang)
    - [discogs](#discogs)
    - [google](#google)
    - [lastfm](#lastfm)
    - [spotify](#spotify)
    - [stackoverflow](#stackoverflow)
    - [urban](#urban)
    - [wiki](#wiki)
    - [youtube](#youtube)
  - [special](#special)
    - [add-flag](#add-flag)
    - [blacklist](#blacklist)
    - [error](#error)
    - [guilds](#guilds)
    - [list-bugs](#list-bugs)
    - [make-tunnel](#make-tunnel)
    - [reloadservice](#reloadservice)
    - [reloadstructures](#reloadstructures)
    - [restart](#restart)
    - [set-afk](#set-afk)
    - [set-status](#set-status)
    - [simulate](#simulate)
    - [update-bug](#update-bug)
    - [update](#update)
    - [view-bug](#view-bug)
  - [tickets](#tickets)
    - [ticket](#ticket)
  - [util](#util)
    - [feature-request](#feature-request)
    - [groups](#groups)
    - [help](#help)
    - [how-to](#how-to)
    - [message-preview](#message-preview)
    - [null](#null)
    - [ping](#ping)
    - [report-bug](#report-bug)
    - [unknown-command](#unknown-command)
  - [Collected data](#collected-data)

## animals

### birb

Shows an image of a birb

### cat

Shows an image of a cat

### dog

Shows an image of a dog

### fox

Shows an image of a fox

### kangaroo

Shows an image of a kangaroo

### koala

Shows an image of a koala

### panda

Shows an image of a panda

### racoon

Aliases: `raccoon`, `raccon`

Shows an image of a racoon

### redpanda

Aliases: `red-panda`

Shows an image of a redpanda

## anime

### awooify

Aliases: `awoo`

Awooifies someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | user | who to awooify? |

### baguette

Eats a baguette.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | who shall eat the baguette? |

### cry

Cries.

### ddlc

Aliases: `dokidokiliteratureclub`, `ddlcscene`

Creates a DDLC scene. Body can be 1 or 2 for monika, 1/1b/2/2b for others.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| character | string | which character to use? |
| background | string | which background to use? One of `bedroom`, `class`, `closet`, `club`, `corridor`, `house`, `kitchen`, `residential` and `sayori_bedroom`. |
| face | string | which face to use? A-R for monika, A-Z for natsuki, A-Y for sayori and A-X for yuri. |
| text | string | what should the character say? |

### declare

Declares communism.

### drink-coffee

Aliases: `drinkcoffee`, `animecoffee`, `anime-coffee`

Someone enjoying warm coffee.

### gah

gah image

### hug

Hugs someone.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | who do you want to hug? |

### kanna

kanna image

### kannagen

Generates a kannagen image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what to kannafy? |

### kemonomimi

Kemonomimi image

### kiss

Kisses someone.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | who do you want to kiss? |

### lick

Licks someone.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | who do you want to lick? |

### lolice

Aliases: `loli`, `lolies`

Lolice rules

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| lolice | user | who's the lolice? |

### neko

Neko image

### pout

Pouts

### quote

Shows random anime quote

### safebooru

Random safebooru image.

### shrug

Shrugs.

### sip

Sips

### slap

Slaps someone.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | who do you want to slap? |

### smug

Feelin smug.

### sofurry

Random image from sofurry

### waifu

Shows random non-existent waifu generated by AI

## dev

### apm

Gets info about Atom Text Editor package

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| pkg | string | Which Atom package to get info about? |

Usage: `apm <pkg>`

### caniuse

Searches caniuse.com for support

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| name | string | Which feature to search for? |

### chart

Generates a simple chart. Uses quickchart.io

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| args | string | what data to visualize? |

### code

Aliases: `http-code`, `error-code`

Explanation for given http status code.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| code | integer | What code to get info about? |

Usage: `code <code>`

### color

Aliases: `colour`, `color-preview`, `colour-preview`

Preview what a color looks like. Accepts HEX, RGB(A) and predefined HTML colors

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| value | string | What color do you want to view? |

Usage: `color <value>`

### djs

Searches in discord.js docs

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| query | string | Enter query to search for |
| source | string | Source version to use |

Usage: `djs <query> [source]`

### dstatus

Shows status of discord services.

### embed

Sends a thumbnail based on given JSON

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| embed | string | JSON embed to show |

### emotes

Aliases: `emoji`, `emote`

Shows info about an emoji

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| emote | string | Emote to get info about |

### format

Aliases: `markdown`

Shows information about formatting messages

### is-emoji

Returns if given message has an emoji or not

### logme

Shows properties of sent image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| argument | string | string :) |

### lolcode

EXECUTEZ GIVEN LOLCODE CODE. STDIN IZ EMPTY

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| code | string | WUTS TEH CODE 2 EVAL? |

### npm

Gets info about NPM package

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| pkg | string | Which NPM package to get info about? |

Usage: `npm <pkg>`

### php

Shows information from PHP documentation. Use either `php <class | function>` or `php <class>::<method>`. Use object oriented style when available.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| php | string | Which class/function to get info about? |

Usage: `php help`

### pip

Gets info about Python Package on PIP Package

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| pkg | string | Which PIP package to get info about? |

Usage: `pip <pkg>`

### request

Aliases: `req`

Makes a new HTTP request

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| method | string | Which method to use? Type `help` for more info. |
| url | string | Which URL to make request on? |
| format | string | What's the format to use? `json` or `text`. |

Usage: `req get http://danbulant.eu/ text`

### uptime

Aliases: `up-time`

Shows uptime of igni

## economy

### balance

Aliases: `bal`

Shows yours BBS balance. More in `info user`

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| target | member | Which user to get balance from? |

### beg

Begs users to give you BBS

### invest

Invest BBS into the economy

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| sum | float | How much to invest? |

### investments

Aliases: `investment`

Shows your investments. Use `investment <number>` to see details of single investment.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| investment | integer | Which investment to show? |

### leaderboard

Aliases: `top`, `ranks`

Shows the users with top rank.

### mine

Mines BBS, once per 12 hours.

### pay

Pays someone BBS

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | Who to pay? |
| amount | float | What amount to pay? |

### rank

Aliases: `level`, `lvl`

Shows your or someone else's current rank and rank points.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user to get level from? |

### rich

Aliases: `richest`, `baltop`

Shows rich people

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| page | integer | Page to look at |

### search-internet

Aliases: `search-places`, `search-net`, `net-search`

Searches virtual internet for BBS

### top-counters

Aliases: `counting-top`

Lists the top counters

### top-inviters

Shows top inviters.

### withdraw-investment

Withdraws an investment

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| id | integer | What's the number of investment? See `investments` command for more. |

### xp

Aliases: `exp`

Shows your or someone else's current level and experience

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | which user to get level from? |

## essentials

### achievements

List all your achievements

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | What's the user you want to list achievements of? |

### afk

Set a message to display when someone pings you.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| message | string | What message to display? |

### avatar

Aliases: `av`, `pfp`

Shows yours (or someone else's) avatar

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | User to check on? |

### close-tunnel

Closes existing tunnel

### convert

Converts a currency to another one

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| number | float | How much to convert? |
| source | string | What currency to convert from? |
| target | string | What currency to convert to? |

### count

Aliases: `user-count`, `member-count`

Shows information about members of this server

### covid

Aliases: `covid19`, `corona`, `coronavirus`, `covidinfo`, `coronainfo`

Shows recent information about COVID-19

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| country | string | which countrys stats do you want to see? |

Usage: `covid [country]`

### fact

Shows random useless fact

### flags

Aliases: `badges`

Shows list of user flags

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| member | member | which user to get flags from? |

### invite

Shows bot invite link

### last-ping

Aliases: `pong`, `ponged`

Shows who last pinged you.

### math

Aliases: `calc`, `calculator`

Calculates given math expression

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| expression | string | What expression to calculate? |

### oldest

Aliases: `old`

Shows oldest users on discord

### random-avatar

Aliases: `random-pfp`, `random-av`

Shows a random avatar

### randomcolor

Aliases: `random-color`

Shows a random color

### reddit

Aliases: `meme`, `memes`, `puppy`, `dankmeme`, `dankmemes`, `cursedimage`, `cursedimages`, `foodporn`

Gets random image from given subreddit. Can be used with or without r/

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| reddit | string | Which subreddit to get the image from? |

### reddituser

Aliases: `ru`

Fetch information about a reddit user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | string | which reddit user to fetch info from? |

### request-tunnel

Aliases: `contact-developers`

Requests a message tunnel to devs. DM only.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| context | string | Why do you want to contact developers? |

### stats

Aliases: `statistics`, `about`, `status`

Statistics and information about igni

### subinfo

Aliases: `sub`, `subreddit`

Fetch information about a subreddit

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| sub | string | which subreddit to fetch info from? |

### translate

Aliases: `t`

Translate string or previous message

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| target | string | What language to translate to? Use 2 letter language code. |
| text | string | What text to translate? |

### voted

Aliases: `vote`

Checks your vote status

### wttr

Aliases: `weather`, `wttr.in`

Shows current weather

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| city | string | What's the city to show weather info for? |

## fun

### ascii

Aliases: `figlet`

Makes ascii text. For list of fonts, see [figlet.js](https://github.com/patorjk/figlet.js/).

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What text should the bot render? |

Usage: `ascii [font] <text>`

Examples:

- ascii Hello there
- ascii Bloody Booo

### catfact

Aliases: `cat-fact`, `catfacts`

Shows a random fact about cats.

### clap

Aliases: `clapify`

Clapify given text

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | Text to clapify |

### coinflip

Aliases: `cf`

Flips a coin.

### cool

Cool up something

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| cool | string | What do you want to cool? |

### cow

Ascii cow saying or thinking whatever you want

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| variant | string | Variant to use, think or say? |
| text | string | Text to make cow say/think: |

### dab

DAB

### dadjoke

Shows random dad joke

### impostor

Who was the impostor?

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | Who was the impostor? |

### joke

Shows random joke

### kill

Kills user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user to kill? |

### leetify

Aliases: `leet`

Leetify your text

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | Text to leetify: |

### lenny

Everyone knows what's lenny

### reversetext

Aliases: `reverse`

Reverses given text

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What text to reverse? |

### rps

Aliases: `rockpaperscissors`, `rock-paper-scissors`

Plays rock paper scissors game with bot.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| chose | string | What do you choose? One of `rock`, `paper` and `scissors` |

### say

Make the bot say what you want

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | What do you want bot to say? |

### snipe

Display a recently deleted message

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| number | integer | Which number of recently deleted messages should the bot show? |

Usage: `snipe [msg number]`

### snipelist

Aliases: `snipes`

Display list of channels with recently deleted messages

Usage: `snipelist`

### spoiler

Aliases: `spoil`

Make the bot say something in annoying spoilers

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | What to say: |

### subscript

Converts text to subscript

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What text to convert? |

### superscript

Converts text to superscript

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What text to convert? |

### throw

Throws a random object at someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member-lax | Who to throw at? |

### topic

Shows a random topic

### vaporwave

Aliases: `vaporify`

Vaporify given text

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | What to vaporify? |

## games

### apexuser

Aliases: `au`

Fetches info about given Apex legends player

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| player | string | which player to fetch? |
| platform | string | which platform to use (PC, PS4 or X1)? |

### mastermind

Starts a game of mastermind.

### mc

Aliases: `mcnick`, `mcnickname`, `minecraftname`

Shows history of mc username

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| name | string | What minecraft username to get info about? |

### osuuser

Aliases: `ou`, `osu`

Shows information about osu user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | string | which user to search for? |
| type | string | what mode to use? |

### pokedex

Aliases: `pokemon`

Finds pokémon in pokedex

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| poke | string | What pokemon do you want to find? |

### skin

Shows skin of given user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| username | string | Enter username of the minecraft player to show skin of: |

### trivia

Aliases: `quiz`

Asks a question

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| type | string | What difficulty to use? Use `any` for any difficulty and `stats` to show your statistics. |
| fast | boolean | Do you want to end the trivia after you respond? This will disable the multiplayer. |

### wouldyourather

Aliases: `wyr`

Shows a would you rather question/

## giveaway

### end-giveaway

Aliases: `g-end`, `giveaway-end`

Ends a giveaway

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| message | string-integer | What's the message ID of giveaway? |
| channel | channel | What's the channel of giveaway? |

### reroll-giveaway

Aliases: `g-reroll`, `giveaway-reroll`

Rerolls a giveaway

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| message | string-integer | What's the message ID of giveaway? |
| channel | integer | What's the channel of giveaway? |

### start-giveaway

Aliases: `g-start`, `giveaway-start`

Starts a giveaway

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| time | time-length | After how long should the giveaway end? 0 for manual ending. (Example: 1hour, 2mins) |
| item | string | What item do you intend to giveaway? 200 characters maximum. |
| channel | text-channel | Which channel to send the giveaway to? |
| winners | integer | How many winners should be selected? |
| messages | natural-number|optional | How many messages does the user need to have sent to be able to apply? `skip` if no requirement. |
| invites | natural-number|optional | How many people does the user need to have invited to be able to apply? `skip` if no requirement. |
| roles | role-list|optional | What roles does the user need to have to be able to apply? Reply with role names or IDs, separated by space. `skip` if no requirement. |
| server | invite|optional | What server does the user need to have to join to be able to apply? Reply with invite link. `skip` if no requirement |

## image

### facepalm

Aliases: `face-palm`

Facepalms

### pat

Pats someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | Who to pat? |

### wink

Winks to someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | Who to wink to? |

### achievement

Creates a minecraft-like achievement, thanks to alexflipnote.dev

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What achievement did you get? |

### blurpify

Blurpifies an image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | image | what to blurpify? |

### captcha

Captchifies someone.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | who shall be in captcha? |
| text | string | what is in the captcha? |

### changemymind

Aliases: `mind`

Try and change my mind.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what are you sure about? |

### clyde

Aliases: `clydify`

Make clyde say something.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what to say? |

### coffee

Random coffee image from alexflipnote.dev

### deepfry

Deepfries an image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | image | what to deepfry? |

### endtask

Aliases: `stopworking`, `sw`

Ends a task

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what task to end? |

### fone

Shows random image from happy fone api

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| type | string | Enter type of resource |

### food

food image

### gay

Makes image or someone more gay

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | image | What image/Who to make gay? |

### glass

Makes image or someone more glass

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | url|user | What image/Who to glassify? |

### iphonex

Puts an image into iphonex

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | image | what to put into iPhone X? |

### jpeg

Aliases: `jpg`, `jpegify`

JPEG-ify someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| character | user | who to jpegify? |

### lookingback

Aliases: `lookback`, `lookingbackat`, `lookbackat`

How dare he look at her.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user2 | user | who do you want to look at? |
| user | user | who is looking back? |

### magik

Aliases: `magikify`

Magikifies an image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | image | what to magikify? |
| intensity | integer | what's the intensity to use? |

### makeameme

Aliases: `makememe`, `genmeme`

Make a meme using imageurl/avatar toptext botomtext

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | user|url | Image URL to make meme of: |
| top | string | Top text of meme: |
| bottom | string | Bottom text of meme: |

### phcomment

Makes an phcomment

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what to comment? |

### qr

Aliases: `qrcode`

Makes a QRCode from given text

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | Text to encode into QRCode |

Usage: `qr <text>`

### salty

Makes an image more salty, thanks to alexflipnote.dev

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | url|user | What image to salty? You can also send a username. |

### sauce

Aliases: `saucenao`, `source`, `sourceimage`

I need the sauce. Nao!

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | url | Which image to search for? |

### stickbug

Stickbugs an image

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | image | What to stickbug? |

### tenor

Shows a tenor GIF.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| title | string | what should be the title? |
| type | string | What should the bot search for? |
| description | string | What should be the description? |

### threats

Aliases: `threat`

Shows 3 biggest threats.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | who's the 3rd thread? |

### trap

Traps someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | who to trap? |

### trash

Shows trash waifus

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | user | Who's the trash here? |

### triggered

Aliases: `trigger`

Triggers an image or someone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | url|user | What image/Who to trigger? |

### trumptweet

Aliases: `tweet`, `trump`

So what did trump tweet today?

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | what did trump tweet?? |

### wasted

Makes image/user wasted

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| image | url|user | What image/Who to waste? |

### whowouldwin

Aliases: `whowins`, `wouldwin`, `whowin`

Compares who would win.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user2 | user | who do you want to compare? |
| user | user | who should be the other one to compare? |

### xkcd

Aliases: `comic`

Shows todays xkcd comic.

### ytcomment

Makes a youtube comment

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What to comment? Max 999 characters |

## mod

### alias

Aliases: `add-alias`

Adds an alias to a command

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| target | command | What command to alias to? |
| source | string | What alias to add? Must contain only non-whitespace characters. |

### alter-automod

Edits automod configuration

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| option | string | Which option to change? One of bannedWords, mentions, regexes, invites, links, emojis, spoilers and selfbots. |
| action | string|optional | What action should the bot take? `skip` to remove the rule. One of kick, ban, warn, softban and messageDelete. |
| settings | string | What are the additional settings? List of words separated by space for bannedWords, number for emojis or mentions. |

### alter-perms

Aliases: `edit-perms`, `alter-permissions`, `edit-permissions`

Edits permissions

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| role | role | What role to edit? |
| channel | channel|optional | What text channel or category to edit? Skip to edit global permissions. |
| cmd | command|group|optional | What command or group to edit? Skip to edit all commands. |
| value | boolean|string | Enable the command? Yes, no or message to show instead of the generic permission denied. |

### announce

Aliases: `announcement`

Make the bot announce what you want.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| title | string | What's the title of announcement? |
| string | string | What do you want to announce? |
| color | string | What's the color you want to use? |
| showAuthor | boolean | Do you want to show you as author? |

Examples:

- announce "Title" "Description" blue

### auto-react

Creates, updates or removes auto reactions

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | text-channel|optional | What channel to auto react in? `skip` for current. |
| reactions | emojis|optional | What reactions to react with? `skip` to remove auto reactions. If multiple, split them by space (` `). |

### automod

Shows automod configuration

### ban

Bans a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user do you want to ban? |
| reason | string | why do you want to ban this user? |

Usage: `ban <user> <daysToDeleteMessages> <reason>`

### case

Shows an offender case

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| case | integer | which case do you want to view? |

### channels

Lists allowed channels or sets/removes them

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| option | string | Please select an option: `<add | remove | clear>` |
| channels | channel | Which channels to add/remove? |

### clear-perms

Aliases: `clear-permissions`

Clears all the servers permission overwrites

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| confirmation | string | WARNING - this will delete all the servers permission overwrites! Are you sure? Type `confirm` to confirm. |

### clearsettings

Clears all the guilds settings

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| confirmation | string | WARNING - this will delete all the guilds cases and other settings! Are you sure? Type `confirm` to confirm. |

### counting

Aliases: `counting-channel`

Creates or deletes counting channel

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | text-channel | Which channel to use? |
| remove | boolean | Do you want to remove the channel as counting channel? |

### edit-embed

Aliases: `embed-edit`

Edits given command

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| message | message | What's the message id of the embed to edit? Only bots messages can be edited. |
| type | string | What to edit? |
| value | string | What's the new value to set? |

### history

Shows on offenders history

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | which users offense history do you want to view? |

### import

Imports data from aztec

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| code | string | What's the code from aztec? Use the `igni` command in Aztec to get the code. |

### info

Aliases: `roleinfo`, `ri`, `channelinfo`, `chi`, `channel`, `serverinfo`, `si`, `server`, `guildinfo`

Gets information

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| command | string | Which resource you want to get info about? |
| pointer | role|channel | which role/channel to get info about? |

Usage: `info help`

### kick

Kicks a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user do you want to kick? |
| reason | string | why do you want to kick this user? |

### lock

Locks channel

### logs

Aliases: `log`

Log settings. See `help` subcommand for more info. When altering, use +option to add, -option to remove and !option to toggle log options

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| command | string | Which action to do? Send `help` if not sure. |
| channel | channel | Which channel to add/remove? |
| settings | string |  |

### media-lock

Aliases: `medialock`

Updates media lock for given channel

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | channel|optional | Which channel to media lock? `skip` for this. |
| options | options | Which media lock options to use? `clear` to remove media lock. |

### media-locks

Aliases: `medialocks`, `list-media-locks`

List all enabled media locks

### mute

Mutes a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| member | member | which user do you want to mute? |
| reason | string | why do you want to mute this user? |

### perms

Aliases: `permissions`

Views permissions for current or given channel

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | text-channel|category-channel | Which channel to view permissions of (text or category channels only)? |

### poll

Create simple polls with igni.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| title | string | what is the title of the poll? |
| args | string | what should be the options? Use format `<emoji> option`. Duplicates will be ignored. |

### purge

Deletes a certain amount of message in channel.

Examples:

- purge 10
- purge 15min
- purge bots 50
- purge embeds 10h

### random-member

Aliases: `randommember`, `random`

Selects random member

### reaction-roles

Aliases: `rr`

Creates a reaction role

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | text-channel|optional | In which channel is the message? `skip` to use this. |
| message | string | What's the message ID to check? |
| reaction | emoji | What's the reaction to accept? |
| role | role | What's the role to give/remove? |

### reason

Aliases: `editreason`

Warns a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| case | integer | which case do you want to edit? |
| reason | string | what should the new reason be? |

### removewarn

Remove a warn from a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| case | integer | which warn case do you want to remove? |

### role

Aliases: `r`, `roles`

Add, remove or toggle a role on a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| option | string | Please select an option: `<add | remove | toggle>` |
| user | member | Which user would you like to select? |
| role | role | Which role would you like to select? |

### rrm

Aliases: `reaction-roles-message`

Creates a reaction roles message

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | text-channel|optional | What's the channel to send the message to? `skip` to use this. |
| reactions |  | What are the reaction roles? Reply in format of `<emoji> <role> <message>`. Send multiple entries each in it's own message. |

### settings

Manages bot settings. User settings in DMs, otherwise server settings. Replace spaces in setting names with dashes (-) or quote them.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| group | string | What's the setting group to show? |
| setting | string | Which setting to show? |
| value | string | What to set the setting's value to? |

### softban

Softbans a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user do you want to softban? |
| reason | string | why do you want to softban this user? |

Usage: `softban <user> <daysToDeleteMessages> <reason>`

### stats-channels

Aliases: `statistics-channels`, `stats-channel`

Sets statistics channels.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| operation | string | What operation do you want to comence? Use list to show stats channels. |
| channel | channel | What channel to update? |
| name | string | What to set as the name of channel? |

Usage: `Use list to view all set up channels. Add to add a channel (and set it's name as 3rd argument). Remove to remove a channel from updating, clear to remove all.`

### unban

Unbans a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | string-integer | which user do you want to unban? |
| reason | string | why do you want to unban this user? |

Usage: `unban <user> <reason>`

### unlock

Unlocks channel

### unmute

Unmutes a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| member | member | which user do you want to unmute? |
| reason | string | why do you want to unmute this user? |

### warn

Warns a user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | which user do you want to warn? |
| reason | string | why do you want to warn this user? |

### welcomechannel

Aliases: `leavechannel`, `joinchannel`, `welcome-channel`, `welcome-messages`

Sets welcome and leave channels. Overwrites previous settings.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| channel | channel | which channel to log into? |
| type | string | which actions to log (both, leave or join)? `clear` to remove the channel. |

## music

### clear-queue

Clears the music queue

### jump

Aliases: `skip-to`

Jumps to selected position in queue

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| number | integer | To which position in queue to jump to? |

### leave

Aliases: `disconnect`, `dc`, `fuckoff`

Leaves the voice channel.

### loop

Aliases: `lq`, `loop-queue`, `loop-song`, `loop-off`

Loops queue or current song

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| mode | string | What to loop? One of `song`, `queue` and `off`. |

### move

Moves a song in the queue

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| song | integer | Which song number to move? |
| target | integer | To which position to move the song to? |

### now

Aliases: `np`, `now-playing`

Show current playing song

### pause

Pauses playback

### play

Aliases: `p`, `fuckon`, `pt`, `play-next`, `join`

Add given music into queue

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | string | What music to add? |

### queue

Aliases: `q`

List current queue

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| selected | integer | Which song to get info about? |

### remove

Remove song from queue

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| selected | integer | Which song to remove from queue? |
| length | integer | How many songs to delete? |

### resume

Resumes playback

### save-song

Sends you the current song details into DMs

### seek

Seeks playback

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| seek | integer | How much to seek? Use `h:m:s` format (hours and minutes are optional) |
| absolute | boolean | Seek from start? yes/no. |

### shuffle

Shuffles the queue

### skip

Skips currently playing song(s)

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| number | integer | How many songs to skip? |

### stop

Stops the music player

### volume

Aliases: `vol`

Sets music volume

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| volume | integer | What to set the new volume to? |

## scircles

### invited

Aliases: `invites`

Shows the user you or mentioned user invited.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | Which user should be used for searching? |

### profile

Aliases: `user`, `member`, `who-am-i`, `who-is`, `user-info`

Shows user profile

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | member | What user to get info about? |

### scircles-description

Aliases: `set-description`

Sets your description

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What's your new description? |

### set-timezone

Sets your timezone

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| timezone | timezone | What's your timezone? |

### timezones

Shows an image heatmap of timezones used

### tz-list

Aliases: `timezones-list`

Lists timezones and their users.

## search

### bang

Aliases: `ddg`, `duckduckgo`

Shows link to duckduckgo bang or shows instant answer

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | What to try searching on DDG instant answers / bangs? |

### discogs

Searches discogs

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What to search for? |

### google

Shows link to search given text on google

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| string | string | What to google? |

### lastfm

Aliases: `lfm`

Searches LastFM

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What to search for? |

### spotify

Searches spotify

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| search | string | What to search? |

### stackoverflow

Aliases: `stack`, `so`

Searches in StackOverflow.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| filter | string | What to search for? |

### urban

Aliases: `ud`, `define`, `df`

Find the meaning in the Urban Dictionary

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| text | string | What is the word do you want to look up? |

Usage: `urban <text>`

### wiki

Aliases: `wikipedia`

Extracts some information from Wikipedia page.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| page | string | Which page to extract information? |

### youtube

Searches youtube for videos

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | string | What to search for? |

## special

### add-flag

Aliases: `toggle-flag`

Add flag to user

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | which user to give flag to? |
| flag | string | which flag to add? |

### blacklist

Prohibit a user from using this bot

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| option | string | Please select an option: `<add | remove | clear>` |
| users | user | Which users to add/remove? |

### error

Shows details about an error/leave

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| code | user|string | which error code/user to get info about? |

### guilds

Lists guilds igni is in

### list-bugs

Lists known bugs

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| type | string | Which bugs to list? |

### make-tunnel

Creates a tunnel in this server to selected user.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| user | user | What user to connect this channel to? |

### reloadservice

Aliases: `reload-service`, `service-reload`

Reloads service

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| service | string | which service to reload? |

### reloadstructures

Reloads structures - useful when structures were updated during update

### restart

Restarts the bot

### set-afk

Toggles the bots afk status

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| afk | boolean | Please select an AFK option? (true/false) |

### set-status

Set the bots activity/status

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| type | string | Which kind of status? |
| name | string | What should the status be? |

### simulate

Simulates given event

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| event | string | which event to start? |

### update-bug

Updates given bug. Accepts shell arguments

### update

Updates the bot

### view-bug

Views given bug report.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| bug | string | Which bug report to view? |

## tickets

### ticket

Aliases: `tickets`

Create or manage a ticket. Use `create` to create a new ticket (or with no arguments). Use `close`, `save`, `open` or `delete` in the ticket channel.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| subcommand | string | which subcommand would you like to use? |
| ticket | string | what's the ticket id? |

## util

### feature-request

Aliases: `feature-request`

Requests a feature for the bot

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| feature | string | What feature to request? Be as precise as possible. |

### groups

Aliases: `list-groups`, `show-groups`

Lists all command groups.

### help

Aliases: `man`, `commands`

Displays a list of available commands, or detailed information for a specified command

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| command | group-or-command | Which command or command group do you want details about? |

Usage: `help [command | command group]`

Examples:

- help
- help prefix

### how-to

Aliases: `usage`

Shows information about how to use the bot

### message-preview

Previews a message.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| url | url|message | What's the message link? |

### null

Aliases: `d`

Does nothing, can be used as a target for aliases

### ping

Checks the bot's ping to the Discord server.

### report-bug

Aliases: `bug-report`

Reports a bug in igni.

**Arguments**:

| Name | Type | Prompt |
| --- | --- | ----- |
| bug | string | What bug to report? Be as precise as possible. |

### unknown-command

Displays help information for when an unknown command is used.

Examples:

- unknown-command kickeverybodyever

## Collected data

The bot requires some data to be recorded to it's databases. Apart from settings you explicitly set using commands, the following data is recorded:
* Guild name, id, join date and member count (used for statistics and possibly propagation, once we will start using it for propagation we will add a way to disable it)
* Member message count (used for rank) - contains just the total message count and bot-generated values like level
* Invites (used for invite tracking) - Contains user ID, server ID, invite code, expiration date and uses
* Error logs when an error is triggered in a command (users will see an error message) - message ID, their tag, channel ID and server ID
* Anonymized public statistics - total servers added and removed each day (just the numbers). This is the only data that's always public.

By adding the bot, you allow the collection of data specified above as well as any command used. We're also not liable for any data saved into the bot.

To delete all data of a server, you can use the `clearsettings` command. To delete data of a user or member, contact the devs via the support server. To request a dump of your data, contact developers via the support server. The bot is operated from United States and hosted in NYC.