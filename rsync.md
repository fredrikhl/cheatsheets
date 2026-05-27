# rsync

```bash
# copy file into dir
rsync /path/to/file remote:/path/to/dir/

# copy a directory
rsync -r /path/to/dir remote:/path/to
rsync -r /path/to/dir/ remote:/path/to/dir/
```


## Keep remote dir in sync with local dir

```bash
rsync --recursive --delete --times --owner --group --chmod=a+r /path/to/src/ /path/to/dest/
```


## Options

Arhive (`--archive`) defaults

- `--recursive` (`-r`) - copy directory trees
- `--links` (`-l`)- preserve symlinks
- `--perms` (`-p`) - preserve permissions
- `--times` (`-t`) - preserve mtime (required for "partial sync")
- `--owner` (`-o`) - preserve owner
- `--group` (`-g`) - preserve group


Other options

- `--delete` - delete remote files (when syncing dirs)
- `--copy-links` (`-L`) - copy symlink targets
- `--atimes` (`-U`) - preserve atime
- `--crtimes` (`-N`) - preserve ctime
- `--chmod=` - set permissions - e.g. `--chmod='Du=rwx,g=rw,o-rwx,Fa=r'`
- `--compress` (`-z`) - use compression
- `--verbose` (`-v`, `-vv…`) - verbosity


Superuser

- `--super` - force rsync to (try) running superuser actions (e.g. set owner)
- `--fake-super` - do select superuser actions using a work-around
- `--no-super` - don't run any superuser actions
