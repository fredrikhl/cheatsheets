# openssl server

Set up a `nc`-like SSL server on port `<port>` with certificate `<pemfile>` and
private key `<keyfile>`:

```bash
openssl s_server -accept <port> -cert <pemfile> -key <keyfile>
```

# openssl client

Connect to an SSL server with a `nc`-like SSL client:

```bash
openssl s_client -connect <host:port>
```

* `-debug`: Show debug info
* `-showcerts`: Show all certificates in chain presented by server
* `-key`: Use private client key
* `-CAfile <file>`: Use CA certificate in (PEM) `<file>`

## Connect to server and show certificate info
```bash
echo | \
  openssl s_client -connect <hostname>:<port> 2> /dev/null | \
    awk '/-----BEGIN/,/END CERTIFICATE-----/' | \
      openssl x509 -noout -text
```

## Pipe request body
```bash
echo "GET / HTTP/1.1\n\n" | openssl s_client -connect <host>:<port> -ign_eof
cat /path/to/file.request | openssl s_client -connect <host>:<port> -ign_eof
```
