# od

Dump binary data in hex/oct/...

```bash
od [file]

# hexdump-like
od -A x -t x1z -v [file]

# basic hexdump
od -A n -t x1 -v [file]
```


## Offsets

- `-A d` - decimal offsets
- `-A o` - octal offsets
- `-A x` - hex offsets
- `-A n` - no offsets


## Formats

- `-t xN` - N-byte hex
- `-t oN` - N-byte octal
- `-t dN` - N-byte signed decimal
- `-t uN` - N-byte unsigned decimal


## Endianness

- `-endian little`
- `-endian big`
