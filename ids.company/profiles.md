---
layout: default
toc: true
footer: (c) <a href="https://ids.company">ids.company</a> 2021
---
# Profiles

## General info

Profiles should be saved into Jem (which should then be used for connecting other services to user account).

They should contain the following:

* name (directly tied to discord tag, possibly just have option to include the discriminator)
* description (some sort if public bio)
* viewable (so users can choose who can view their profile)
* avatar (might as well be tied to discord avatar)
* possibly background (depends on the style of profile pages; possibly premium only)
* badges (for verified developers, igni developers, bug hunters...)

And other optional fields (e.g. birth date, gender...) that may or may not be public.

## Finding friends

The bot could be used for finding friends or people with similar interests - the base function could be searching for people in same server who have a game account connected to their jem/discord one. Additionally, the bot could also search for people of a set gender or around given age (not exact).

### Skill level

For games, the bot could also save "skill level" of sorts (for games where it's possible, their global rank) and then could sort people who have similar skill levels.

## Moderation

Profiles should be also used for global moderation of sorts - when user gets banned in a server, it could broadcast that ban and it's reason to other servers (and could be visible in user's history).

This function should be controlled to not be abused, so for example only servers with member count above a certain treshold would broadcast their bans/kicks/warns.

It should be also usable in automoderation (for example if the user is frequently flagged as a bot, igni should require higher verification minimum, or when a user is frequently warned for spamming igni should give higher sanctions).

## Privacy

Actions should have access to these profiles only limited and as per settings. Only the discord info itself (name, avatar), description (if profile set to public or if action ran from user) and the banner. Other fields only when action explicitly requests and is verified (and are allowed to do so).
