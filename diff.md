# diff

```bash
# To view the differences between two files:
diff -u version1 version2

# To view the differences between two directories:
diff -ur folder1/ folder2/

# To ignore the white spaces:
diff -ub version1 version2

# To ignore the blank lines:
diff -uB version1 version2

# To ignore the differences between uppercase and lowercase:
diff -ui version1 version2
```


## ignore

* `-B`: ignore blank lines
* `-b`: ignore whitespace
* `-E`: ignore tab expansion
* `-W`: ignore trailing spaces
* `-w`: ignore all whitespace diffs
* `-I <regex>`: ignore regex matches


## test

```bash
# To report whether the files differ:
diff -q version1 version2

# To report whether the files are identical:
diff -s version1 version2
```


## recursive

```bash
# List files
diff -rq folder1/ folder2/

# Show diffs
diff -ENwbur folder1/ folder2/

# Exclude files
diff -rq -x .git -x '*.pyc' folder1/ folder2/
```
