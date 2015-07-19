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
eval "$(nodenv init -)"
```

## Global install

To install nodenv for usage by all users on the system, this will provide
the proper environment variables to be set on login shells. Setting the group
ownership allows members of the group, below creates a new group, you can use
a pre-existing one also. To add a user to this group `usermod -aG nodenv user`

```
git clone -b v0.3.3 https://github.com/wfarr/nodenv.git /usr/local/lib/nodenv
sudo /usr/sbin/groupadd nodenv
sudo chgrp -R /usr/local/lib/nodenv
sudo chmod g+ws /usr/local/lib/nodenv
```

Then add teh following to `/etc/profiled.d/nodenv.sh`

```
export NODENV_ROOT=/usr/local/lib/nodenv
export PATH=$NODENV_ROOT/bin:$PATH

eval "$(nodenv init -)"

# Make sure locally install binaries get priority
export PATH=node_modules/.bin:$PATH
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

### Usage with Node.js
```
# Use 0.8 versions
nodenv install v0.8.28

# Use 0.10 versions
nodenv install v0.10.38

# Use 0.12 versions
nodenv install v0.12.2

```

### Usage with io.js
```
# Use any io.js version
nodenv install iojs-v1.6.4

# You can also install the latest version of io.js
nodenv install iojs
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
