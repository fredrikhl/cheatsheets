# uniq

Remove/process duplicate lines from file or stdin.

`uniq` only deals with adjacent duplicate lines, and is often used in
combination with `sort` to deal with *all* duplicate lines in a file.

`sort -u` and `sort | uniq` has similar effects (see `sort` for more info):

```bash
sort -u <file>
sort <file> | uniq
```


## Examples

```bash
# omit duplicate lines
sort file | uniq -u

# only show duplicate lines
sort file | uniq -d

# count unique lines
sort file | uniq -c
```
