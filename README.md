# nodenv

rbenv, but for node.

## Installation

To install the latest stable release:

```
git clone -b v0.3.3 https://github.com/wfarr/nodenv.git ~/.nodenv
```

Then add the following to your shell config at the end:

```
export PATH="$HOME/.nodenv/bin:$PATH"
eval "(nodenv init -)"
```

## Usage

```
» nodenv help
Usage: nodenv <command> [<args>]

Some useful nodenv commands are:
   exec        Execute a command from a particular NodeJS version.
   shell       Set NODENV_VERSION for the lifetime of a shell.
   local       Persist the preferred NodeJS version in the cwd.
   global      Persist the preferred NodeJS default version.
   install     Install a version of NodeJS.
   uninstall   Uninstall a version of NodeJS.
   version     Show the current NodeJS version.
   versions    Display all versions of NodeJS installed in `${NODENV_ROOT}/versions/*'.
   rehash      Rehash nodenv shims (run this after installing executables)

See `nodenv help <command>' for information on a specific command.
```

## Credits

This library was heavily, heavily, heavily inspired by
[@sstephenson](https://github.com/sstephenson)'s
[rbenv](https://github.com/sstephenson/rbenv) and
[ruby-build](https://github.com/sstephenson/ruby-build) projects.
A few ideas were also taken from [nvm](https://github.com/creationix/nvm).

A number of patterns and utilities are borrowed from that project,
and it is my hope that nodenv provides the same simplicity,
elegance, and usability that I've come to love in rbenv and ruby-build
for NodeJS users.
