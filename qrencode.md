# qrencode

Generate QR codes.

```
qrencode [OPTION]... [STRING]
```

- <https://fukuchi.org/works/qrencode/>
- <https://github.com/fukuchi/libqrencode/>


## Settings

- `-l {L, M, Q, H}` — error correction level (Low … High)
- `-m <margin-size>`
- `-s <pixel-size>` (
- `-v <version>` - Version/capacity (1 … 40)


## IO

- To read: `-r <filename>`.  Default is stdin, if no input string is given.
- To write: `-o <filename>`, `-o -`.  Writes to stdout by default.


## Formats

Set output format with `-t <format>`:

- PNG, PNG32 (use `-d <dpi>` to set DPI)
- EPS, SVG, XPM
- ASCII, ASCIIi
- ANSI, ANSI256
- UTF8, UTF8i, ANSIUTF8, ANSIUTF8i, ANSI256UTF8


## Examples

```bash
echo 'Hello, World!' | qrencode -t ANSI256 -o -

echo 'Hello, World!' | qrencode -t PNG -s 10 -m 5 -v30 -l Q -o /tmp/file.png
```
