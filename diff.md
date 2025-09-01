# diff


## find file diffs in directories

```bash
# show diff for each file
diff -r <dir1> <dir2>

# only report file names that differs
diff -rq <dir1> <dir2>

# only report file names that are identical
diff -rs <dir1> <dir2>
```


## ignore vcs

```bash
diff -x .svn -x .git -x .hg -x CVS …
```


## count differing lines

```bash
diff … | grep '^[<>]' | cut -d' ' -f1 | sort | uniq -c
```


## ignore minor changes

```bash
# ignore the whitespace:
diff -b …

# ignore blank lines:
diff -B …

# ignore trailing whitepace
diff -W …

# ignore all whitespace
diff -W …

# ignore case:
diff -i …

@ ignore certain patterns:
diff -I <regex> …
```
