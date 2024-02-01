# lz

LZMA-compression.

```bash
# create lzip archive of file
# (this will keep the source fille, equivalent to gzip -k)
lz4 file.txt  # file.txt.lz4
lz4 file.txt file.lz4

# create archive and remove source (equivalent to gzip)
lz4 --rm file.txt  # file.txt.lz4
lz4 --rm file.txt file.lz4

# output a compressed file to stdout
lz4cat file.txt.lz4
lz -dcfm file.txt.lz4
```


## options

* `-z` - compress (default)
* `-d` - decompress
* `-c` - output to stdout
* `-f` - force (overwrite destination files, passthrough unknown files)
* `-m` - "multiple files"?
* `-<n>` - for `<n>` 1-12 - sets compression level (default: 1)
