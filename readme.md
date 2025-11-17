# dotfiles

Version control common configuration files. They can be installed in different ways.

# .bashrc.will

If a `~/.bashrc` already exists simply 'source' this from the end of that file.

```bash
source <path_to_repo>/.bashrc.will
```

If one does not exist create one, so machine specific config does not
need to pollute this common file.

# .vimrc.will

As with `.bashrc` we can simply source this from the primary `.vimrc` location (`~/.vimrc`, or `$MYVIMRC`)

If this is sourced at the top, then **machine specific** config can be added below and should overwrite.

```bash
source <path_to_repo>/.vimrc.will 
```

## vim plugins

Vim plugins can be managed using the `vim-plug` (itself a plugin). This can be installed manually, with instructions [here](https://github.com/junegunn/vim-plug)
but basically just copy the contents of [this file](https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim) into `.vim/autoload`

Plugins are added in the code block

```bash
plug#begin()

# add plugins here

plug#end()

```

and can then be directly installed in Vim by running the command `:PlugInstall`. See [the github readme](https://github.com/junegunn/vim-plug) for all the instructions

# Git

Unlike the others, this is a set of **git commands** which, when run, will configure git globally.

I have included settings which are generally always useful. Clearly others can be added either globally, or more locally to projects
as required.

To set, simply run

```bash
./gitconfig.will
```

On Windows, assuming we are using git bash or similar, would have to execute with bash explicitly

```shell
bash gitconfig.will
```

One thing that is not included is username and email. When making a commit Git will prompt you to set these, if you have not. You can
do this with

```
git config --global user.name <your name>
git config --global user.email <your email>
```

Another omitted setting is `autocrlf` which can cause issues with line endings. On Windows this should (almost always) be

```
git config --global autocrlf=true
```

whereas on Linux this should be


```
git config --global autocrlf=input
```

These should be set as the defaults.

If you get in an absolute mess, you can inspect what the line endings are as follows

```
git ls-files --eol
```

And can sort out files that are messed up with

```
git add <file> --renormalize
```

