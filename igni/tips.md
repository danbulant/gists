---
layout: default
toc: true
footer: (c) Copyright <a href="https://ids.company">ids.company</a> 2021.
---
# Tip and tricks

## Command edits

Any message can be edited and the bot will take it as a new one. You can use this to "edit" commands and the bot will update it's reply. Works for 30 seconds after the message was sent.

This can be used to update typos in announcements, fixing command name or fixing prefix (editing the message to use correct prefix will run the command).

Another way to use this to your advantage is to traverse the `settings` command, like (each line can be an edit just adding content):

* `settings` - lists all the groups
* `settings moderation` - lists all settings in `moderation` group
* `settings moderation muterole` - shows current value for the setting
* `settings moderation muterole muted` - Sets the setting to new value (sets `muterole` setting in `moderation` to the role `muted`)

**Keep in mind that every message edit is like running a new command.** Remember it especially when banning or doing other destructive actions.
