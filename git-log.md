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


## Formatting

```
--pretty=<format>
    default: medium
    formats: oneline, short, medium, full, fuller, reference, email, raw,
             format:<string>, tformat:<string>

    See the "PRETTY FORMATS" section for some additional details for each format. When =<format> part is omitted, it defaults to medium.

--abbrev-commit
--no-abbrev-commit
   shortened commit ids

--oneline
   This is a shorthand for "--pretty=oneline --abbrev-commit" used together.
```
