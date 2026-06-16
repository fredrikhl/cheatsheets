ss
==
Utility to investigate sockets


Selection
---------
- `-4`, `-6` — ipv4, ipv6
- `-u`, `-t` `-x` — udp, tcp, or unix sockets
- `-l` — only listening sockets


Output
------
- `-n` — numeric addresses instead of hostnames
- `-p` (`-T`) — process (and thread) using socket
- `-Q` — suppress queue statistics


Examples
--------
```
# Show listening TCP sockets
ss -tlnpQ

# show all sockets connecting to 192.168.2.1 on port 80
ss -tnQ dst 192.168.2.1:80

# show all ssh-related connections
ss -tnQ state established '( dport = :ssh or sport = :ssh )'
```
