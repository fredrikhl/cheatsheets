# split

Split a large file into smaller files

```bash
split [opts] [INFILE] [PREFIX]
```

```bash
# Split into files of 1000 lines:
split -l 1000 <file>

# Split a large binary file into 10M files:
split -b 10M <file>

# To consolidate split files into a single file:
cat x* > <file>
```

```bash
# Split file.txt into files file-nn.txt of line length 100
split -l 100 --additional-suffix=.txt file.txt file-
```
