# ack

Text finder: `ack <pattern> [<file|dir>...]`


## Matching

`ack PATTERN` *or* `ack --match PATTERN`.
Exclude potentially matching lines with `--not PATTERN`.

```bash
# find occurences of foo, unless:
#  - immediately followed by 'bar', '_bar', or '-bar'
#  - the line starts with 'import '
ack --not 'foo[-_]?bar' --not '^import ' --match foo
```


## Context

* After: `-A <n>`, `--after-context=<n>`
* Before: `-B <n>`, `--before-context=<n>`
* Both: `-C <n>`, `--context=<n>`


## Filename matching

To ignore certain directory names: `--ignore-dir <name>`.  Example:

```bash
ack --ignore-dir docs --match example
```


To ignore files: `--ignore-file <filter>:<args>`.  Examples:

```bash
# ignore exact filename
ack --ignore-file is:README.md …

# ignore file extensions (case insensitive)
ack --ignore-file ext:md,rst,txt …

# ignore file pattern (case insensitive)
ack --ignore-file match:readme(.(md|rst|txt))? …

To ignore files based on first line (e.g. hash-bang, case insensitive)
ack --ignore-file firstlinematch:/bash/ example
```

To only include certain file types:

```bash
ack -t python …
```

Define custom types to only include certain files:

```bash
# only search files named *foo*.txt
ack --type-set='footype:match:.*foo.*\.txt' -t footype <pattern>
```


## Output

* Only list matching files: `-l`
* Only list non-matching files: `-L`


## Encoding

With iconv

```bash
ack $(echo "[æøå]+" | iconv -f utf-8 -t latin1) | iconv -f latin1 -t utf-8
```
