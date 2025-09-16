# sed

## usage

* `-i [backup-suffix]`, `--in-place [backup-suffix]` - edit file in place (with
  optional backup)

* `-r`, `-E`, `--regexp-extended` - use extended regex


## modifiers

### d: discard

```bash
# To remove empty lines and print results to stdout:
sed '/^$/d' file.txt
```

### p: print

Prints matches
```bash
# To search and replace, and only print matched lines:
#   option -n -- do not print lines
#   modifier 'p' -- print matches
sed -n 's/^foo \([a-z]+\) baz$/\1/p'
```

## Search and replace

```bash
# To replace all occurrences of "day" with "night" and write to stdout:
sed 's/day/night/g' file.txt

# To replace all occurrences of "day" with "night" within file.txt:
sed -i 's/day/night/g' file.txt

# To replace all occurrences of "day" with "night" on stdin:
echo 'It is daytime' | sed 's/day/night/g'

# To remove leading spaces
sed -i -r 's/^\s+//g' file.txt

# To replace newlines in multiple lines
sed ':a;N;$!ba;s/\n//g'  file.txt
```

## Prepend text to file

```bash
# Caveats:
# - If file only contains one line, text will appended?
# - If file is empty, nothing happens
sed -i '0,/^/ {
    h
    r/dev/stdin
    g
    N
}' <file> <<EOT
<text here>
EOT
```
