# CVS hate

## Revert file

```bash
# Check file history
cvs log path/to/file

# Check file rev diff
cvs diff -r good_version -r bad_version path/to/file

# Revert (merge) to good_version
cvs up -j bad_version -j good_version path/to/file

# Commit
cvs commit path/to/file
```


## Remove file

```bash
# Remove file from filesystem
rm path/to/file

# Remove links to file from repository
cvs rm path/to/file

# OR let cvs remove file
cvs rm -f path/to/file

# commit
cvs commit path/to/file
```


## Remove folder

```bash
# Remove each file individually
# E.g. remove path/to/dir with files FileA, FileB

# Remove files from filesystem
rm path/to/dir/File{A,B}

# Remove links to file from repository
cvs rm path/to/dir/File{A,B}

# OR let cvs remove file
rm -f path/to/dir/File{A,B}

# commit
cvs commit path/to/dir
```

## Get status

```bash
cvs -q -n update
```


## Status codes

[CVS status flags](http://www.xinotes.net/notes/note/116/)

| Code  | Meaning    | Description |
|:-----:|------------|-------------|
|   ?   | what?      | It's not a file in CVS. CVS knows nothing about this file |
|   A   | Added      | This is a file you just added to CVS but not yet committed. You have to commit it before others can see it. |
|   C   | Conflicted | A Conflict occurred when you did CVS update. The conflicted lines are marked with special characters and you need to manually resolve the conflicts. |
|   M   | Modified   | You have modified this file. It's different from what's in CVS and you need to commit (check in) the file to persist your changes in CVS. |
|   P   | Patched    | This file was patched when you did CVS update. The effect is the same as U (update), but the changes were so small that CVS decided to send a patch (P) instead of a whole file (U). |
|   U   | Updated    | This file was updated when you ran CVS update. It could be a file that already existed on the local drive, or a new file brought down from the CVS repository. |
|   R   | Removed    | You asked CVS to remove this file but you haven't committed the removal. |

