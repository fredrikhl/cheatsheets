# git rev-list

Show commits in the commit tree of a given ref

```bash
# newest first
git rev-list master

# show current/latest commit
git rev-list --max-count=1 master
git rev-list master | head -n1

# Reverse the order (oldest to newest)
git rev-list --reverse master

# Count the number of commits
git rev-list --count master

# Show commits touching a given file.
git rev-list master -- path/to/file
```


## ahead/behind

```bash
# Shows:
#   1. N commits in A, *not* in B
#   2. N commits in B, *not* in A
git rev-list --left-right --count A...B
```
