# Pretty print the json
```bash
jq "." filename.json
```

# Access the value at key "foo"
```bash
jq '.foo'
```

# Access first list item
```bash
jq '.[0]'
```

# Slice & Dice
```bash
jq '.[2:4]'
jq '.[:3]'
jq '.[-2:]'
```

# Get 'name' for each object in list 'accounts'
```bash
jq '.accounts[] | .name'
```

# Objects

## Translate

To filter an object, and translate object key:

```bash
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '{foo: .foo, bar: .baz}'
```

## Delete attribute

```bash
# blacklist 'foo'
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= del(.foo)'
```

```bash
# whitelist 'foo', 'bar'
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= {foo, bar}'
```
