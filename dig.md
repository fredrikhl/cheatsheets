# dig

```bash
dig [ @ns ] name [ TYPE ]

# example
dig @ns1.uio.no example.org ALL
```

## Reverse lookup

```bash
dig -x <addr>
```

## special types

- ANY
- ALL

## Filters

Only include the answer section:

```bash
dig +noall +answer name
```
