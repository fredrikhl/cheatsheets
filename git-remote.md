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


## delete a remote branch

```bash
git push <remote> --delete <branch-name>
```
