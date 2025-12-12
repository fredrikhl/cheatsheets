# jq

Basic use:

```bash
jq . filename.json
cat filename.json | jq .
```


## Accessing attributes and items

```bash
# the value at key "foo"
echo '{"foo": "bar"}' | jq '.foo'

# first item of a list
echo "[1, 2, 3, 4]" | jq '.[0]'

# slice lists
jq '.[2:4]'
jq '.[:3]'
jq '.[-2:]'

# Get 'name' for each object in list 'accounts'
jq '.accounts[] | .name'
```


## Transforming objects

```bash
# create new objects
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '{a: .foo, b: .baz}'
# → {"a":"FOO", "b":"BAZ"}

# filter - 'blacklist', remove attribute
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= del(.foo)'

# filter - whitelist 'bar', 'baz'
echo '{"foo": "FOO", "bar": "BAR", "baz": "BAZ"}' | jq '. |= {bar, baz}'
```


## Key value pairs

```bash
echo '{"accounts": {"foo": {"id": 3}, "bar": {"id": 4}}}' |
  jq -r '.accounts | to_entries[] | {name: .key, id: .value.id}'
# → {"name": "foo", "id": 3}
# → {"name": "bar", "id": 4}
```

Wrap the whole expression in `[<expr>]` to wrap the output in a list.


## String interpolation

```bash
jq -r '.users[] | "\(.last | ascii_upcase), \(.first)"' <<EOF
{"users": [{"first": "Stevie", "last": "Wonder" },
           {"first": "Michael", "last": "Jackson"}]}
EOF
# → WONDER, Stevie
# → JACKSON, Michael
```


## Functions

Some useful functions

```bash
# timestamps and dates
echo 1796480116 | jq r '. | todateiso8601'
# → 2026-12-05T14:15:16Z

# arithmetic
echo 30937043 | jq r '"\(. / (60 * 60 * 24) | floor) days"'
# → 358 days
```
