# memcached


## connect

```bash
telnet <host> <port>
```

## commands

```
# stats
stats

# slabs
stats slabs

# slab list
stats items

# list keys
stats cachedump <slab> <num|0>

# get value
get <key>

# delete key
delete <key>

# quit
quit
```
