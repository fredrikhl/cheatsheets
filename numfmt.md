# numfmt

```bash
# convert from IEC (human readable file/disk size) to integer
numfmt --from=iec

# convert from integer to IEC
numfmt --to=iec
```


## Examples

```bash
# Emulate `df -h` with `numfmt`:
df | numfmt --header=1 --from-unit=1024 --field=2-4 --to=iec
```

```bash
# Parse `df -h` output
df -h | numfmt --header=1 --field=2-4 --from=iec
```

```bash
# Sum available disk space
df -h \
    | tail -n +1 \
    | tr -s " " \
    | cut -d' ' -f 3 \
    | numfmt --from=iec \
    | awk '{s+=$1} END {printf "%.0f\n", s}' \
    | numfmt --to=iec
```
