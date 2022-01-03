# git clean


## dry-run

```bash
# dry-run
git clean -n

# force
git clean -f
```


## selection

```bash
# recurse into subdirs
git clean -d

# *only* remove untracked gitignored files
git clean -X

# *also* remove untracked gitignored files
git clean -x
```


### Examples

```bash
# remove all untracked files
# (force, remove directories, ignore .gitignore)
git clean -f -d -x
```
