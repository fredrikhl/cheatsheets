# ack


## Context

* `-A <n>`, `--after-context=<n>`
* `-B <n>`, `--before-context=<n>`
* `-C <n>`, `--context=<n>`


## Ignore

* `--ignore-dir <dir>`
* `--ignore-file <file>`


## Only include given file name patterns

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
