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


## inspect entry

```bash
# show status
git stash show [n]

# show diff
git stash show -p [n]
```


## apply entry

```bash
# apply and remove entry (if successful)
git stash pop [n]

# apply entry without removing it
git stash apply [n]
```


## create branch

Create a branch from stash entry, but apply it to the last commit from which the
entry was created (i.e. avoids conflicts with local changes in the working tree)

```bash
git stash branch <name> [n]
```
