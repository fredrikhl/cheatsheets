# Bash redirect IO

## stderr as stdout

```bash
# stdout → stderr
>&2 echo "foo"
echo "foo" 1>&2

# stderr → stdout
echo "foo" 2>&1

# when combining with other redirects,
# stdout/stderr must come last.  E.g. suppress all output:
{ echo "foo"; >&2 echo "bar"; } >/dev/null 2>&1
```

## Process Substitution

Stdout as file-input

```bash
cat <(ls -l)
diff -y <(ls) <(ls -a)
```


## here-string

Any string as stdin:

```bash
read -r <<< Hello
read -r <<< "$PATH"
read -r <<< "$(ls -l)"
```


## here-document

Multiline string as stdin:

```bash
cat <<EOF
USER: ${USER}
HOME: ${HOME}
EOF
```

Without substitution:

```bash
cat <<'marker'
USER: ${USER}
HOME: ${HOME}
marker
```

Suppress leading *tabs*:

```bash
cat <<-EOF
	Line 1
	Line 2
EOF
```

Can be used with the null command to "comment out" blocks of code:

```bash
: <<COMMENT
echo "this will not run"
touch file
COMMENT
```
