# dotfiles

Version control common configuration files. They can be installed in different ways.

# .bashrc.will

If a `~/.bashrc` already exists simply 'source' this from the end of that file.

```
source <path_to_repo>/.bashrc.will
```

If one does not exist, it is probably easier to create one, so machine specific config does not
need to pollute this common file.

# .vimrc.will

As with `.bashrc` we can simply source this from the primary `.vimrc` location (`~/.vimrc`, or `$MYVIMRC`)

If this is sourced at the top, then **machine specific** config can be added below and should overwrite.

```
source <path_to_repo>/.vimrc.will ~/.vimrc
```

# .gitconfig.will

Unlike the others, this is a set of **git commands** which, when run, will configure git globally.

I have included settings which are generally always useful. Clearly others can be added either globally, or more locally to projects
as required.

To set, simply run

```
gitsettings
```

On Windows, assuming we are using git bash or similar, would have to execute with bash explicitly

```
bash gitsettings
```

One thing that is not included is username and email. When making a commit Git will prompt you to set these, if you have not. You can
do this with

```
git config --global user.name <your name>
git config --global user.email <your email>
```
