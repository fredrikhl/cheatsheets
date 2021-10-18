# smbclient

```bash
# To display public shares on the server:
# smbclient -L <hostname> -U%
```

```bash
# connect to a share
smbclient //<hostname>/<share> -U<username>%<password>
```

## copy to share

```
# single file
smbclient <connect> -c "put <src> <dest>"

# recursive
smbclient <connect> -c "mput <src> <dest>"
```
