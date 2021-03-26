# Bash parameter expansion

```bash
# More info
info bash Basic 'Shell Expansions' 'Shell Parameter'
```

## Defaults / empty tests

| syntax            | if $var   | result        |
|-------------------|-----------| --------------|
| `${var-default}`  | undefined | "default"     |
| `${var:-default}` | empty     | "default"     |
| `${var=default}`  | undefined | var="default" |
| `${var:=default}` | empty     | var="default" |
| `${var?"error"}`  | undefined | error         |
| `${var:?"error"}` | empty     | error         |
| `${var+default}`  | defined   | "default"     |
| `${var:+default}` | empty     | "default"     |


```bash
# get default if empty
echo "${var:-default}"  # 'default', var=''

# set default if empty
echo "${var:=default}"  # 'default', var='default'

# error if empty
echo "${var:?'not set'}"  # bash: var: not set

# set default if empty
echo "${var:+default}"  # '', var=''
var=nonempty
echo "${var:+default}"  # 'default', var='nonempty'
```


## Substring expansion

| syntax              | from  | result                         |
|---------------------|-------|--------------------------------|
| `${var#pattern}`    | front | remove shortest 'pattern'      |
| `${var##pattern}`   | front | remove longest 'pattern'       |
| `${var%pattern}`    | back  | remove shortest 'pattern'      |
| `${var%%pattern}`   | back  | remove longest 'pattern'       |
| `${var/pat/sub}`    | any   | replace first 'pat' with 'sub' |
| `${var/pat/sub}`    | any   | replace all 'pat' with 'sub'   |
| `${var:offset}`     | any   | strip offset chars from start  |
| `${var:offset:len}` | any   | take len chars from offset     |


```bash
# remove suffix
file="index.html"
echo "${file%.html}.txt"  # index.txt

path="/path/to/file.ext"
echo "${path%/*}"  # /path/to

# remove prefix
file="index.html"
echo "backup${file#index}"  # backup.html

path="/path/to/file.ext"
echo "${path##*/}"  # file.ext

# replace substring
text="foo bar foo"
echo "${text/foo/baz}"  # baz bar foo

text="foo bar foo"
echo "${text//foo/baz}"  # baz bar baz

# index
text=1234567890
echo "${text:4}"  # 567890
echo "${text: -4}"  # 7890

echo "${text:4:2}"  # 56
echo "${text:2:-2}"  # 345678
echo "${text: -2:2}"  # 90
echo "${text: -2:-2}"  #

echo "${text::4}"   # 1234
echo "${text::-4}"  # 123456
```


## list defined vars

```bash
echo "${!SHELL*}"  # SHELL SHELLOPTS
```


## upper/lower

| syntax             |       | result                           |
|--------------------|-------|----------------------------------|
| `${var,}`          | lower | first char                       |
| `${var,pattern}`   | lower | first char if it matches pattern |
| `${var,,}`         | lower | all chars                        |
| `${var,,pattern}`  | lower | all chars that matches pattern   |
| `${var^}`          | upper | first char                       |
| `${var^pattern}`   | upper | first char if it matches pattern |
| `${var^^}`         | upper | all chars                        |
| `${var^^pattern}`  | upper | all chars that matches pattern   |

```bash
text='hello world'
echo ${text^}   # Hello world
echo ${text^^}  # HELLO WORLD
echo ${text^^l} # heLLo worLd
```
