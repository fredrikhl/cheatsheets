# Options

Set shell options using `set` and `shopt`


# set

[[GNU bash set builtin documentation]]

## usage

```bash
# Set/unset xtrace
set -x  # set
set +x  # unset
# Set/unset xtrace by option name
set -o xtrace  # set
set +o xtrace  # unset
```

## options

* `±x`, `±o xtrace`: Print all executed commands
* `±e`, `±o errexit`: Exit on first non-zero status.


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

  [GNU bash set builtin documentation]: https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html
  [GNU bash shopt builtin documentation]: https://www.gnu.org/software/bash/manual/html_node/The-Shopt-Builtin.html
