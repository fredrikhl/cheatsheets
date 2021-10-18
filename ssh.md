# ssh

## socks5 tunnel

```bash
# make a socks5 proxy tunnel at localhost:<port> to <target>
ssh -C2q -D <port> <target>
```

## Port forwarding

```bash
# expose a given port <rport> on <target> on localhost <lport>
ssh <target> -L <lport>:localhost:<rport>

# expose a remote <rhost:rport> through a proxy <proxy>
ssh -fL <lport>:<rhost>:<rport> <proxy> -N
```

## Useful options

```bash
ssh -X  # tunnel x session
ssh -Y  # tunnel x session, trusted
ssh -t  # tty-allocation, repeat to force (`ssh -tt')
ssh -A  # forward authentication agent
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


## Config

```
Host bitbucket
    Compression yes
    HostName bitbucket.org
    User git
    IdentityFile ~/.ssh/<key-file>

# Forwarding
Host springboard
    HostName <hostname>

Host target
    ProxyCommand ssh springboard nc %h %p 2>/dev/null
```

