# Knowledge Node CLI (kn)

The Knowledge Node CLI Utility addresses the needs of most knowledge
workers by providing an easy-to-use command (`kn`) combined with a
modular framework that can be easily customized. It fulfills the design
goals outlined in the Knowledge Exchange Grid (KEG)
[specification](https://github.com/afkworks/keg) (an project from
Association of Federated Knowledge Workers).

## Environment Variables

Environment variables are used both for the `kn` utility itself and,
when necessary, to pass information to an Action script called by
the `kn` tool when passing an argument does not make sense.

Name|Description|Default|Required
|:-:|-|-|:-:
KN|Full path to current local knowledge node|None|Required (per KEG)
KNPATH|Comma-separated list of full paths to local knowledge nodes|None|Optional

### `KN`

`KN` is the only mandatory environment variable. It indicates the full
(absolute) path to a root knowledge node. All other `kn` configuration
specifics can be read from `kn.yml` file there.

### `KNPATH` 

The optional `KNPATH` contains all the full paths to multiple root
knowledge nodes on the current system. `KN` can then be changed to point
to one of these as the active local context for all knowledge work using
the `kn` command. This is somewhat akin to "workspaces" in VS Code and
other IDEs. 

### Relation Between `KN` and `KNPATH`

Changing `KN` to anything other than something listed in the
`KNPATH` (if it exists) is considered a fatal error and the `kn` utility
will stop working. This allows `KNPATH` to be used as a validation of
things that change `KN` as a layer of protection. Even though `KNPATH`
is optional when only one node is used on a system, it is therefore
usually desirable to set them both even if it only contains a single
root knowledge node path.

## The `kn.d` Directory

The special `kn.d` directory contains all of the public Actions used by
the `kn` command. The standard location for this directory is in the
same directory as the `kn` command itself, wherever that is. In
addition, if there is a `kn.d` directory within the root directory of
the currently active knowledge node it will also be included and have a
higher priority than the standard one installed with the `kn` tool
itself. This provide a modular way for knowledge workers to extend and
customize any Action available to `kn` and ensures that anyone reviewing
or using the node on KEG will also have access to those customizations.

## Frequently Asked Questions

These are questions. They are frequent.

### Why Perl?

In short, always use the best tool for the job, and Perl --- despite the
rampant, uninformed shade thrown at it --- is without any doubt the best
tool for this job. If you don't understand why Perl is the best possible
pick for rapid prototyping that involves a lot of text manipulation and
matching, learn why and then consider re-asking your question after you
have a fucking clue.

Mostly because `\p{Cc}`, that's Unicode regular expression support in
case you haven't see it before. Only Perl (the undisputed ruler of
regular expressions) supports it, and frankly anything that needs full
Unicode support and parsing *requires* it. 

### How can I share my knowledge nodes? 

That would be what [`keg`](https://github.com/afkworks/keg) is for.
