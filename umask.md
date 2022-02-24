# umask

Set default file permissions


```
# to show current
umask

# to set umask
umask 0022

# to execute a command with a temporarily changed umask, use a subshell
(umask 027 && touch file)
```


## Masks

```
$ (umask 0 && touch file && mkdir dir && ls -ld file dir)
drwxrwxrwx.  …  dir
-rw-rw-rw-.  …  file
```

```
$ (umask 27 && touch file && mkdir dir && ls -ld file dir)
drwxr-x---.  …  dir
-rw-r-----.  …  file
```
