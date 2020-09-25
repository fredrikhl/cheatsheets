# ln

## Symlinks

```bash
# re-use same name
ln -s path/to/file

# give a different name to the symlink
ln -s path/to/file link-name

# replace existing symlink or file
ln -sf path/to/file
```

To create symlinks in specific directories:

```bash
# example setup
cd /tmp && mkdir foo bar && touch foo/target

# create a bar/target -> ../foo/target
ln -s ../foo/target -t bar

# create a bar/link -> ../foo/target
ln -s ../foo/target -T bar/link
```
