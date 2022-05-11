# systemd-cat

Send stdout/stderr to journal:

```bash
systemd-cat -t my-test --priority info --stderr-priority err <command>
<command> | systemd-cat -t my-test -p notice
```

- `-t`, `--identifier`
- `-p`, `--priority`
- `--stderr-priority`
- `--level-prefix=1`


## Priority

0. emerg
1. alert
2. crit
3. err
4. warning
5. notice
6. info  (default)
7. debug


## Set priority by prefix

```bash
{
  echo "<5>Hello";
  echo "<3>World";
} | systemd-cat --identifier my-test --level-prefix=1
```
