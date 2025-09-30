# grep

## usage

```bash
grep pattern [file]
```

* `-i` - case insensitive
* `-n` - line numbers
* `-v` - exclude matching lines


## extended regex

* `-E`  - use extended regex

```bash
grep "object u\?'\([-_0-9A-Za-z]\+\)'"
grep -E "object u?'([-_0-9A-Za-z]+)"
```


## recursive search

```bash
grep -R pattern path
```

- `-l` - only show file names with matches
- `-L` - only show file names without matches


## read search patterns from file

```bash
grep -f pattern-file …
```
