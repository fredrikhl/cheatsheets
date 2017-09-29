# patch

## create patch using diff

```bash
# Single file
diff -u original modified > original.patch

# Directory tree
diff -rupN original/ modified/ > original.patch
```

Options:

  * diff -r     Recursive
  * diff -u[N]  Include N (default 3) lines of context
  * diff -N     Treat new files as empty files
  * diff -p     For C, show which function change applies in


## create patch using git

```bash
# Between files
git diff --patch original modified > original.patch

# Between commits
git diff --patch commit1 commit2 > commit1.patch
```


### Git, last commit

```bash
git show > patch
```


## Apply

```bash
# Apply patch to single file
patch original < original.patch

# Apply patch to directory tree
patch -p1 < original.patch

# Undo
patch -p1 -R < original.patch
```
