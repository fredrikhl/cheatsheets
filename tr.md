# tr

`tr [options] SET1 [SET2]`


## translate

Replace characters with other characters

```bash
echo abcde | tr "ae" "-"  # → -bcd-

# truncate SET1
echo abcde | tr -t "ae" "-"  # → -bcde

# split pathsep into newlines
echo $PATH | tr ":" "\n"
```


## squeeze (`-s`)

Remove repeating characters

```bash
echo aabbccddee | tr -s "bcd"  # → aabcdee
echo "foo    bar" | tr -s " "  # → foo bar
```


## delete (`-d`)

Remove characters

```bash
echo aabbcc | tr -d "ab"  # -> cc
```


## complement (`-c`)

Replace anything NOT in `SET1`


```bash
# note the inclusion of newline
echo  "abcde" | tr -c "ae\n" "-"  # -> a---e
```
