# Globs

- *.foo
- ?.bar
- [A-Z]*.baz


## extglob

```bash
# set
shopt -s extglob
# unset
shopt -u extglob
# check
shopt -p extglob
```

- ?(pattern-list) : Matches zero or one occurrence of the given patterns
- *(pattern-list) : Matches zero or more occurrences of the given patterns
- +(pattern-list) : Matches one or more occurrences of the given patterns
- @(pattern-list) : Matches one of the given patterns
- !(pattern-list) : Matches anything except one of the given patterns
