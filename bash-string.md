# strings

## slice

```bash
# first two chars
${foo::2}

# minus the first two chars
${foo:2}

# last two chars
${foo:${#foo}-2}

# minus the last two chars
${foo::${#foo}-2}
```
