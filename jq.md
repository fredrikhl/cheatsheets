# jq

    jq . filename.json
    cat filename.json | jq .


## access some value

```bash
# the value at key "foo"
echo '{"foo": "bar"}' | jq '.foo'

# first item of a list
echo "[1, 2, 3, 4]" | jq '.[0]'
```

## slice & dice

```bash
jq '.[2:4]'
jq '.[:3]'
jq '.[-2:]'
```

## Get 'name' for each object in list 'accounts'

```bash
jq '.accounts[] | .name'
```


# Objects

```bash
# extract items from an object
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '{a: .foo, b: .baz}'
# → {"a":"FOO", "b":"BAZ"}
```

## Filter attributes

```bash
# blacklist 'foo'
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= del(.foo)'

# whitelist 'bar', 'baz'
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= {bar, baz}'
```
