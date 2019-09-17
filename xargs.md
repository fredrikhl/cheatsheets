# xargs

build and execute command lines from standard input

## simple usage

```bash
# run command with arguments from stdin
echo -e "foo\nbar\nbaz\n" | xargs echo
# equivalent to 
echo foo bar baz
```

## group arguments

```bash
# run command with N arguments per command
echo -e "foo\nbar\nbaz\n" | xargs -n2 echo
# equivalent to 
echo foo bar
echo baz
```

```bash
# one command per N line of input
echo -e "foo\nbar\nbaz\n" | xargs -L2 echo
# equivalent to
echo foo bar
echo baz
```

## debug

```bash
# use -t to print the resulting commands
echo "foo bar baz" | xargs -t echo
echo "foo bar baz" | xargs -d' ' -t echo
```

## input splitting
```
# null
echo -n -e "foo\0bar\0baz" | xargs -t -0 -n1 echo

# newline
echo -e "foo\nbar\nbaz" | xargs -t -n1 echo

# space
echo -n "foo bar baz" | xargs -t -d' ' -n1 echo
```


## replacement

```bash
# build argument list with a replacement string
echo -e "foo\nbar\n" | xargs -I% echo '[%]'
# equivalent to
echo '[foo]'
echo '[bar]'
```

```bash
# run multiple commands per argument
echo -e "foo\nbar\nbaz\n" | xargs -I% sh -c 'echo "[%]"; echo "{%}";'
# cat files with the filename as a header comment,
# and an extra line separating the files
ls -1 /path/to/files/ | xargs -I% sh -c 'echo "#" "%"; cat "%"; echo ""'
```


## examples

```bash
# find all file name ending with .pdf and remove them
find -name *.pdf | xargs rm -rf

# if file name contains spaces you should use this instead
find -name *.pdf | xargs -I{} rm -rf '{}'

# Will show every .pdf like:
#	&toto.pdf=
#	&titi.pdf=
# -n1 => One file by one file. ( -n2 => 2 files by 2 files )
find -name *.pdf | xargs -I{} -n1 echo '&{}='
```
