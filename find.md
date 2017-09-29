# find

## name

```bash
# by case-insensitive extension (.jpg, .JPG, .Jpg)
find . -iname "*.jpg"
```

## type

```
# directories
find . -type d

# files
find . -type f

# symlinks
find . -type l

# hardlinks, files that are hardlinks to <myfile>
find . -type f -samefile '<myfile>'
```

## permissions

```bash
# find files by octal permission
find . -type f -perm 777

# To find files with setuid bit set:
find . -type f -xdev \( -perm -4000 \) -print0 | xargs -0 ls -l

# find files owned by 'username' and list file information
find . -type f --user=username -ls
```

## depth

```bash
find . -mindepth 1 -maxdepth 3
```

## time

```bash
# find files modified more than 7 days ago and list file information
find . -type f -mtime +7d -ls
```

## execute

```bash
# find files with extension '.txt' and remove them
find ./path/ -name '*.txt' -exec rm '{}' ';'

# find and delete empty directories
find . -type d -empty -exec rmdir '{}' ';'

# find files with extension '.txt' and look for a string into them
find ./path/ -name '*.txt' | xargs grep 'string'

# find files with size bigger than 5 Mb and sort them by size
find . -size +5M -type f -print0 | xargs -0 ls -Ssh | sort -z

# find files bigger than 2 MB and list them
find . -type f -size +20000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```


# examples

## list all files except those in .git directories

```bash
find . '!' -iwholename '*.git*' -type f
```

## find directories without a certain file

Find all python sub-packages without an `__init__.py`

```bash
find . -type d '!' -exec test -e "{}/__init__.py" ';' -print
```

## find and sort by size

```bash
# find files with size bigger than 5 Mb and sort them by size
find . -size +5M -type f -print0 | xargs -0 ls -Ssh | sort -z
```
