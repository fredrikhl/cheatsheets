# watch

Loop command every `n` seconds.

## usage

```bash
watch -n <seconds> <command>
```

## highlight diff

Highlight difference in output

```bash
watch -n 5 -d ls -l
watch -n 5 -d1 ls -l # keep highlight indefinetely
```

## color support

```bash
watch --color -n 5 ls -l --color
```

## act on change

`-b, --beep`: Beep if command has a non-zero exit
`-e, --errexit`: Freeze updates on command error, and exit after a key press.
`-g, --chgexit`: Exit when the output of command changes.


## examples

```bash
# monitor dd progress
watch -n10 -- pkill -USR1 ^dd$
```
