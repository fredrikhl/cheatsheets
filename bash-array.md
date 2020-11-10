# arrays

```bash
declare -a foo  # indexed
declare -A bar  # associative
foo=(foo bar baz bat banan)
bar=([foo]=1 [bar]=2 [baz]=3)
```

Note: arrays cannot be `export`-ed.

## use as argument

```bash
# As a single string
echo "${foo[*]}"

# One string per array item
echo "${foo[@]}"
```


## mutate

```bash
# append two items
foo+=(bar baz)
```


## access

```bash
echo "${foo[1]}"
echo "${bar[baz]}"
```


## slice

```bash
# first two elements
${foo[@]::2}

# minus the first two elements
${foo[@]:2}

# last two elements
${foo[@]:${#foo[@]}-2}

# minus the last two elements
${foo[@]::${#foo[@]}-2}
```


## length

```bash
echo "${#foo[@]}"
```


## indices

```bash
for i in "${!foo[@]}"
do
  echo "$i" "${foo[$i]}"
done
```


## range

```bash
for i in {1..3}; do echo "i=$i"; done
foo=({1..3})
```
