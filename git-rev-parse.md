# git rev-list

Show info on specific commits/refs

```bash
git rev-parse [opts...] [commit-ish...]
```

## Get commit ids
```bash
# get commit-ids
git rev-parse HEAD HEAD~1 main origin/main

# check the given commit-ish is valid and get commit-id
git rev-parse --verify main

# get shortended, unique commit-id prefix
git rev-parse --short HEAD
```

## Get reference/name

```bash
# get unambiguous name for a commit
git rev-parse --abbrev-ref HEAD

# get full path/name for a reference, if one exists
git rev-parse --symbolic-full-name HEAD
```


## List references

```
# List abbreviated reference names (refs/) for...
# all refs
git rev-parse --abbrev-ref --all

# local branches
git rev-parse --abbrev-ref --branches

# remote branches
git rev-parse --abbrev-ref --remotes

# tags
git rev-parse --abbrev-ref --tags
```
