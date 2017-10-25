# Bash redirect IO

## stderr as stdout

```bash
# stdout → stderr
>&2 echo "foo"
echo "foo" 1>&2

# stderr → stdout
echo "foo" 2>&1
```

## Process Substitution

Stdout as file-input

```bash
cat <(ls -l)
diff -y <(ls) <(ls -a)
```
