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
    0) echo '$1==0;;
    1) echo '$1==1;;
    3*) echo '$1==3…' "($1)";;
esac
```

# set

[[GNU bash set builtin documentation]]

## usage

```bash
# set option -n/example
set -n
set -o example
# unset option -n/example
set +n
set +o example
```

## options

* -x,xtrace: Simple trace of calls, shows variable expansion


# shopt

[[GNU bash shopt builtin documentation]]

```bash
# list options
shopt
# set option
shopt -s <option>
# unset option
shopt -u <option>
# query option
shopt -q <option> && echo "set" || echo "unset"
```


# Retrieve N-th piped command exit status
printf 'foo' | fgrep 'foo' | sed 's/foo/bar/'
echo ${PIPESTATUS[0]}  # replace 0 with N

# Lock file:
( set -o noclobber; echo > my.lock ) || echo 'Failed to create lock file'


[GNU bash documentation]: https://www.gnu.org/software/bash/manual/html_node/index.html
[GNU bash set builtin documentation]: https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html
[GNU bash shopt builtin documentation]: https://www.gnu.org/software/bash/manual/html_node/The-Shopt-Builtin.html

