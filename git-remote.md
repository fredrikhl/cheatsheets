# git cheat sheet

Manage remote repositories.


## add / remove a new remote

```bash
git remote add <remote> <url>
git remote remove <remote>
```


## get / set url for remote

```bash
git remote get-url <remote>
git remote set-url <remote> <url>
```


## push to a given remote / branch

```bash
git push <remote> <local-name>
git push <remote> <local-name>:<remote-name>
git push -u <remote> <local-name>:<remote-name>  # Set up tracking for the local repo
```

## set tracking of the current branch

```bash
git branch -u <remote>/<branch>
```

## delete a remote branch

```bash
git push <remote> --delete <branch-name>
```


## find and delete merged branches

```
git branch --remote --merged origin/master --sort 'authordate' \
    | grep -v master \
    | head -n 5 \
    | cut -b 10- \
    | xargs git push --delete origin
```


## find branches by author

```
git for-each-ref --format='%(committerdate) %09 %(authorname) %09 %(refname)' \
    | sort -k5n -k2M -k3n -k4n
```
