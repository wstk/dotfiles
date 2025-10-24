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

If this is sourced at the top, then **machine specific** config can be added below and should (i think) overwrite.

```
source <path_to_repo>/.vimrc.will ~/.vimrc
```

# .gitconfig.will

TBD. Might need to be copied like before. Bit more fiddly.

