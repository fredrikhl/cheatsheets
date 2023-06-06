# hexdump

```bash

# offsets, hex and ascii bytestrings
hexdump -C [file]

# 16 hex bytes pr line
hexdump -e '16/1 " %02x" "\n"' [file]
# ... is equivalent to ...
od -t x1 -An -v [file]
```


## Examples

```bash
# base64-encoded binary 256-bit groups (eg. sha256) to hexbytes
echo -n <b64 data> | base64 -d | hexdump -e '32/1 "%02x" "\n"'
```
