# Knowledge Node Utility (kn), a Framework for Managing Knowledge

The Knowledge Node Utility (`kn`) addresses the needs of most knowledge
workers by providing an easy-to-use command (`kn`) combined with a
modular framework that can be easily customized. It fulfills the design
goals outlined in the Knowledge Exchange Grid (KEG)
[specification](https://github.com/afkworks/keg) (a Association of
Federated Knowledge Workers initiative).

## Designed for Local User

Unlike other installed applications that might require administrator
access, the `kn` approach assumes this command will *always* be within
the full control of the user who is currently logged in. This allows
completely different `kn` tools to be used by each user on the system.
Indeed, the user should be encouraged to customize the `kn` tool to
their needs.

## Never a Package Manager

The emphasis on local user empowerment means it makes no sense to ever
package `kn` in any way. Instead, the `kn` tool and its dependencies
should just be copied or unzipped or symlinked from a users copy of the
`kn` tool. 

Indeed, it is encouraged to simply fork the `kn` project and add its
`bin` directory to the local user's path. That is the extend of any
package management required. 

If a user wants to stay in sync with the master `kn` project repo,
while providing additional plugins they can be added to the `kn`
configuration file.

## Environment Variables

Some environment variables are specified by the KEG initiative, others
are just convenient ways to modularize any `kn` installation.

Name|Description|Default|Required
|:-:|-|-|:-:
KN|Full path to current local knowledge node|None|Required (per KEG)
KNPATH|Comma-separated list of full paths to local knowledge nodes|None|Optional
KNCONF|Full path to kn configuration directory|`${XDG_CONFIG_HOME}/kn`|Optional

## How can I share my knowledge nodes? 

That would be what [`keg`](https://github.com/afkworks/keg) is for.
