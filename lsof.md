# lsof

Lists open files.

```bash
# List all IPv4 network files
sudo lsof -i4

# List all IPv6 network files
sudo lsof -i6

# To find listening ports:
lsof -Pnl +M -i4

# List all processes accessing a particular file/directory
lsof /path/to/file

# List all files open for a particular user
lsof -u <username>

# List open files that have been unlinked
lsof +L1
```

## network

```bash
# List all files/network connections a given process is using
lsof -c <command-name>

# Disable hostname/portname lookup
lsof -nP

# List internet addresses
lsof -i <filter>
```

`<filter>`:

* TCP, TCP:80
* UDP

```bash
# List listening TCP ports
lsof -nP -iTCP -sTCP:LISTEN
```

## list open files
```bash
lsof +fg +D /mount/point | egrep -v EVO  # Open files
```


## more

See [this primer](http://www.danielmiessler.com/study/lsof/) for a number of
other useful lsof tips
