# git tag

`git tag` cheat sheet.


## simple tag

```bash
git tag <tag> [commit-id]
```


## annotated tag

```bash
# Add annotated tag
git tag -a -m <message> <tag> [commit-id]
```


## delete

```bash
git tag -d <tag>

# Remove deleted tags from remote
git push <remote> :refs/tags/<tag>
```


## push

```bash
git push --tags
```
