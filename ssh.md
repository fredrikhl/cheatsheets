# ssh

## Proxy/forwarding

```bash
# Start a Socks5 proxy at localhost:<port>
ssh -D [<addr>]:<port> …

# forward specific socket/port
ssh -L <local-socket>:<remote-socket> …

# e.g. expose `localhost:80` @ example.org as *:8080 locally
ssh -L *:8080:localhost:80 example.org

# forwarding options
#  -f -- go to background when connection is up
#  -N -- don't run any commands
#  -q -- quiet mode
```


## ControlMaster management

```bash
# check connection
ssh -O check <host>

# kill connection
ssh -O exit <host>
```


## Escape sequences

Supported escape sequences:

* `~.`  terminate session
* `~B`  send a BREAK to the remote system
* `~R`  Request rekey (SSH protocol 2 only)
* `~#`  list forwarded connections
* `~?`  escape help message
* `~~`  send the escape character by typing it twice

Notes:

* Escapes are only recognized immediately after newline.
* To kill the current session hit subsequently Enter `↵`, `~`, `.`
* More of these escape sequences can be listed with `↵`, `~`, `?`:
