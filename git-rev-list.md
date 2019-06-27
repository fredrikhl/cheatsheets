# git rev-list

```bash
# Show all commits in the commit tree of master
# From newest to oldest
git rev-list master

# Reverse the order (oldest to newest)
git rev-list --reverse master

# Count the number of commits
git rev-list --count master

# Show commits touching a given file.
git rev-list master -- path/to/file
```
