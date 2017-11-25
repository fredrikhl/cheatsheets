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


## Pack contents of a directory

```bash
# pack from parent folder
tar -cf /path/to/foo.tar -C /path/to/parent target

# pack from folder
tar -cf /path/to/foo.tar -C /path/to/target .
```

### exclude files from tarball

```bash
tar -cf /path/to/foo.tar --exclude=\*.{jpg,png} /path/to/foo/
```

## Unpack contents

### To a given directory

```bash
tar -xf /path/to/foo.tar -C /path/to/target/
```

### Strip parent folder in archive when unpacking

```bash
tar -xf /path/to/foo.tar --strip 1
```
