# xxd

hexdump util

```bash
echo 'Hello, World!' | xxd
```

```bash
echo 'Hello, World!' | xxd
```


## reverse hexdump

```bash
xxd original | xxd -r
od -tx1 -An -v original | xxd -r -p
hexdump -C original | sed 's/^[0-9a-f]\+//' | sed 's/|.*$//' | xxd -r -p
hexdump -e '16/1 "%02x " "\n"' original | xxd -r -p
```


## examples

```
$ # -p: plain mode, no formatting with addr column, etc...
$ echo -n "foo" | xxd -p
666f6f
```

```bash
$ # -c <N>: octets/bytes per column/line (-c)
$ echo -n "foo" | xxd -c1
00000000: 66  f
00000001: 6f  o
00000002: 6f  o
```
