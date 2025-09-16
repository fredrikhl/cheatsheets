# grep

## usage

```bash
grep pattern [file]
```

* `-E`  - use extended regex
* `-i` - case insensitive
* `-n` - line numbers
* `-v` - exclude matching lines

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
