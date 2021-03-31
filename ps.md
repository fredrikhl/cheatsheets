# ps

## Process selection

```bash
# all processes - bsd
ps ax
# all processes - standard
ps -e

# all processes owned by foo
ps -a -u foo
```

## Formatting

```bash
# include user/owner (++) - bsd
ps u
# include user/owner (++) - standard
ps -f

# custom format
ps -o pid,user,command
```

```bash
# process tree/hierarchy - bsd
ps f
# process tree/hierarchy - standard
ps --forest
```

## Tricks

```bash
# exclude grep from your grepped output of ps
ps aux | grep '[h]ttpd'
```
