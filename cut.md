# cut

- delimiter: `-d:`, `-d' '`
- field: `-f3`, `-f1-4`, `-f3-`
- invert: `--complement`


## get field from line

Get the third field delimited by a `:`:

```bash
echo "foo:bar:baz:bat" | cut -d: -f3
# output: "baz"
```


## remove field from line

Invert the selection with `--complement` to get eveything *but* the third field:

```bash
echo "foo:bar:baz:bat" | cut -d: -f3 --complement
# output: "foo:bar:bat"
```


## slice fields

Get fields 2-3, inclusive:

```bash
echo "foo:bar:baz:bat" | cut -d: -f2-3
# output: "bar:baz"
```

Get field 3 and every field after it:

```bash
echo "foo:bar:baz:bat" | cut -d: -f3-
# output: "baz:bat"
```

Get field 2 and every field before it:

```bash
echo "foo:bar:baz:bat" | cut -d: -f-2
# output: "foo:bar"
```
