# nc

nc, ncat, netcat


## client

```bash
# tcp example.com:8080
nc example.com 8080

# udp example.com:8080
nc -u example.com 8080
```

## server

```bash
# bind and listen
nc -l 0.0.0.0 8080

# keep open for multiple connections
nc -lk 0.0.0.0 8080

# bind to unix socket
nc -lU /var/run/example-socket
```

## options

- `-4`: Use IPv4 only
- `-6`: Use IPv6 only
- `-l`: bind and listen for incoming connections
- `-k`: with listen, keep open
- `-p <port>`: set the source port
- `-s <ip>`: set the source ip
- `--broker`: with listen, send all input to all connected clients
