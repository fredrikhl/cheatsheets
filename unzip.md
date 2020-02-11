# unzip


## Exctact

```bash
# Extract archive
unzip archive.zip

# Uncompress to folder
unzip archive.zip -d dir/
```


## Test integrity of archive

```bash
unzip -tq archive.zip
```


## List files and directories in a file

```bash
unzip -l archive.zip
unzip -Z1 archive.zip  # see zipinfo for more
```
