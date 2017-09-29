# tar

## tarball

```bash
# inspect
tar -tvf /path/to/foo.tar

# unpack
tar -xvf /path/to/foo.tar

# pack
tar -cvf /path/to/foo.tar /path/to/foo/
```


## compress

* `-z` -- gzip (`.tar.gz`, `.tgz`)
* `-j` -- bzip2 (`.tar.bz2`, `.tbz2`)


## exclude files from tarball
`tar -cf /path/to/foo.tgz --exclude=\*.{jpg,png} /path/to/foo/`

## To extract folder contents of an archive
`tar -xf /path/to/foo.tar --strip 1`

# To extract contents to a directory
`tar -xf /path/to/foo.tar -C /path/to/target/`
