# tree

Show file tree

```bash
dnf install tree
```

## options

- `tree -L <n>`: limit to *n* subdirectory levels
- `tree --prune`: omit empty directories

## file sizes

- `tree -s`: include size (in bytes)
- `tree -h`: include size (human readable)
- `tree --du [-h]`: - show accumulated size for directories (like `du -c`)


## file timestamps

```bash
tree -D --timefmt "%Y-%m-%d %H:%M:%S" .
```
