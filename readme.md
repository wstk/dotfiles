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

I don't think there is the option to configure the `.vimrc` path beyond the 'standard' locations.

Therefore simply *copy* this file. If changes are made, they can be propagated back to the repo, if needed.

```
cp <path_to_repo>/.vimrc.will ~/.vimrc
```

# .gitconfig.will

TBD. Might need to be copied like before. Bit more fiddly.

