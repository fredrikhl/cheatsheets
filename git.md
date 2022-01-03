# git cheat sheet

Helpful git fixes: <https://ohshitgit.com/>

## Debugging

```bash
GIT_CURL_VERBOSE=1 GIT_TRACE=1 git …
```


## clone

```bash
git clone https://host/path/to/repo [location]
git clone ssh://<user>@<hostname>:<port>/path/to/repo.git [location]
```


## checkout branch

```bash
git checkout -b <local-name> <remote>/<remote-name>
git checkout -t -b <local-name> <remote>/<remote-name>  # Check out and set up tracking
```


## push to a given remote

```bash
git push <remote> <local-name>
git push <remote> <local-name>:<remote-name>
git push -u <remote> <local-name>:<remote-name>  # Set up tracking for the local repo
```


## add/update commit with different permissions

```bash
git update-index --chmod=(-|+)x <file>
```


## Remove staged and working directory changes
```bash
git reset --hard
```


## Reset single file

```bash
git checkout -- <file>
```


## Getting info on a repo
```bash
git ls-remote --heads <git-url>
git ls-remote --tags <git-url>
```


## Submodule

```bash
# Clone with submodules
git clone --recursive

# Checkout submodules in existing repo
git submodule update --init
```


## Undo/redo unpushed commit
```bash
git reset HEAD~   # undo commit, but don't touch working tree
# do changes
git commit -c ORIG_HEAD
```
