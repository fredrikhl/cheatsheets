# loop

```bash
for file in *; do
    echo $file;
done
```

# case

```bash
case "$1"
in
    0) echo '$1==0';;
    1) echo '$1==1';;
    3*) echo '$1==3…' "($1)";;
esac
```


# Retrieve N-th piped command exit status
printf 'foo' | fgrep 'foo' | sed 's/foo/bar/'
echo ${PIPESTATUS[0]}  # replace 0 with N

# Lock file:
( set -o noclobber; echo > my.lock ) || echo 'Failed to create lock file'

# Export variables from an environ file

```bash
export $( grep -v '^\s*\(#\|$\)' /path/to/envvars | xargs )
```

# scoping is broken

```bash
myfunc() {
    myfunc() {
        echo redefined myfunc;
    };
    echo first myfunc;
};
```


[GNU bash documentation]: https://www.gnu.org/software/bash/manual/html_node/index.html
