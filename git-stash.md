# git stash

```bash
# push local working tree changes
git stash

# list stash stack
git stash list

# pop latest or n-th entry from the stack
git stash pop [n]

# remove latest or n-th entry from the stack
git stash drop [n]
```


## Inspect entry

```bash
# show status
git stash show [n]

# show diff
git stash show -p [n]
```


## Apply entry

```bash
# apply and remove entry (if successful)
git stash pop [n]

# apply entry without removing it
git stash apply [n]
```


## Conflicts

To resolve conflicts after a bad `pop`:

```bash
# Resolve conflicts (or do nothing to later checkout original)
# Restore all files (or individual files) to mark conflicts as resolved
git restore --staged -- .
```


Avoid conflicts by popping to a new branch.  This applies the changes to the
commit from which the entry was created, which should avoid most conflicts.

```bash
git stash branch <name> [n]
```
