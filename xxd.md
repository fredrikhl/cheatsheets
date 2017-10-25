# xxd

hexdump util

```bash
echo 'Hello, World!' | xxd
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
