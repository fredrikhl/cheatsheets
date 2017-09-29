# git log

`git log` cheat sheet.


## restrict commits to commits that affects file
```bash
git log --follow <file>
```


## List commits after a given identifier
```bash
git log --reverse --ancestry-path c01a2b3c4d^..master
```
