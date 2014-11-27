
This is a collection of extension:color mappings, suitable to use as your
LS COLORS environment variable. Most of them use the extended color map,
described in the ECMA-48 document; in other words, you'll need a terminal
with capabilities of displaying 256 colors.

As of this writing, around 300 different filetypes/extensions is supported.
That's indeed a lot of extensions, but there's a lot more! Your help is greatly
appreciated.

![bash-it Structred ls](https://github.com/ahmadassaf/configurations/blob/master/screenshots/bash-it_structured_ls.png)

### Guidelines

For files that usually ends up next to each other, like html, css and js,
try to pick colors that fits in nicely together. Filetypes with multiple
possible extensions, like htm and html, should have the same color.

To install and use this file, for **Bash terminal** first we need to define these variables:

**NOTE** If you are using **bash-it** i recommend you put all the following in the `lib\appearance.bash`

```shell
# Adding needed files for dircoloring
export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
export MANPATH="/usr/local/opt/coreutils/libexec/gnuman:$MANPATH"
```

Afterwards you have to add the following:

```shell
eval $( dircolors -b $HOME/LS_COLORS )
```

If you got an error that dircolors is not defined then you have to point it to the `gdircolors` if you have installed the `coreutils` homebrew recipe.

```shell
eval `gdircolors -b ~/.dircolors`
```

ZSH SYNTAX HIGHLIGHTING
=======================
If you have `oh-my-zsh` installed then you have to add to the following file `lib\theme-and-appearance.zsh` (note the `dircolors` or `gdircolors`):

```shell
# Enabling dircolors coloring
eval `gdircolors -b ~/.dircolors`
```

If you are using the installation file in my [main configuration repository](http://github.com/ahmadassaf/Configurations), then this is all done automatically :)

DEVELOPERS
==========

There's a [library][1] written that lets you use various LS COLORS on
arbitary files and directories. A simple implementation can be found [here][2].

Using this, you can do:

```shell
find $HOME -maxdepth 1  | ls_color
mpc search artist Laleh | ls_color
```