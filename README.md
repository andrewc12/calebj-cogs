# andrew.c12 Cogs
#### General, fun and utility modules for [Red-DiscordBot](https://github.com/Cog-Creators/Red-DiscordBot/) v3.

[![discord.py](https://img.shields.io/badge/discord.py-async-blue.svg)](https://github.com/Rapptz/discord.py)
[![Red-DiscordBot](https://img.shields.io/badge/Red--DiscordBot-v3-red.svg)](https://github.com/Cog-Creators/Red-DiscordBot/)

This repo contains cogs I've written, as well as those I've modified and republished when a PR was either unwanted or too drastic of a change from the original cog's scope.

## Table of Contents
* [Installation](#installation)
* [Support and Contact](#support-and-contact)
* [Cog Summaries](#cog-summaries)
* [Cog Documentation](#cog-documentation)
  * [XORole](#xorole)
* [Contributing](#contributing)
* [License and Copyright](#license-and-copyright)

## Installation
Type the following commands into any channel your bot can see, or in a direct message to it.

**1. Adding the repo** - replace `[p]` with your bot's prefix:
```
[p]cog repo add andrew.c12-cogs https://github.com/andrewc12/calebj-cogs/
```

**2. Installing a cog** - replace `[COG_NAME]` with the name of the cog you want:
```
[p]cog install andrew.c12-cogs [COG_NAME]
```

## Support and Contact

## Cog Summaries
* [xorole](#xorole): Self-role functionality with single-membership role sets.

## Cog Documentation

### XORole
XORole was created out of the need for "role sets", which are groups of roles that a member should only have one of at a time. Thus the name, which is short for "exclusive-or roles". Examples use cases include self-assignable color roles, timezone or region roles, and teams (e.g. Ingress or Pokemon Go).

The following user commands are available as subcommands of `xorole`:
* `list`: lists available rolesets and the roles in them.
* `add [role]`: assigns a user a role, removing any others in the same set.
* `toggle [roleset]`: toggle a role on or off, or between a two-role set.
* `remove [role|roleset]`: removes the `role` or their role in `roleset` from the user.

For a roleset of size one, `xorole toggle` will add the role if they don't have it, or remove it if they do. For a roleset of size two, it will toggle between the two roles (one must already be assigned). For other sizes, the command will error.

Calling `[p]xorole [role]` without a valid subcommand is the same as calling `[p]xorole add [role]`.

The cog is configured using the following subcommands of `xoroleset`:
* `addroleset [name]`: creates a new roleset.
* `audit`: lists members that have more than one role in a xorole roleset.
* `autodelete [seconds]`: show or set the auto-delete delay for xorole commands and responses.
  - Max delay 60s. 0 to disable, leave blank to show the current setting.
* `autoswitch [on_off] [rolesets]...`: show or change the autoswitch feature settings.
  - When autoswitch is on, adding a role from a set without using the xorole command will remove any others in that set.
  - Run without parameters to show current autoswitch settings.
  - Both a server default and roleset-specific overrides can be configured.
* `rmroleset [name]`: deletes a roleset.
* `renroleset [old_name] [new_name]`: renames a roleset.
* `addroles [roleset] [role,[role,...]]`: adds a comma-seperated list of roles (or IDs) to a roleset.
* `rmroles [roleset] [role,[role,...]]`: removes a comma-seperated list of roles (or IDs) from a roleset.

## Contributing
Please submit patches to code or documentation as GitHub pull requests!

Contributions must be licensed under the GNU GPLv3. The contributor retains the copyright. I won't accept new cogs unless I want to support them.

## License and Copyright
Except for [scheduler](scheduler/), which is licensed under the [MIT license](scheduler/LICENSE), all code in this repository is licensed under the [GNU General Public License version 3](LICENSE).

Copyright (c) 2016-2018 Caleb Johnson, contributors and original authors.
