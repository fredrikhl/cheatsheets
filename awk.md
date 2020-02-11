# awk

```bash
# sum integers from a file or stdin, one integer per line:
awk '{sum += $1} END {print sum}' \
<<EOF
1
2
3
EOF
```

```bash
# using specific character as separator to sum integers from a file or stdin
printf '1:2:3' | awk -F ":" '{print $1+$2+$3}'
```

```bash
# print a multiplication table
seq 9 | sed 'H;g' | awk -v RS='' '{for(i=1;i<=NF;i++)printf("%dx%d=%d%s", i, NR, i*NR, i==NR?"\n":"\t")}'
```

```bash
# Specify output separator character
printf '1 2 3' | awk 'BEGIN {OFS=":"}; {print $1,$2,$3}'
```

```bash
# count fields per line in a csv file
awk -F ';' '{print NR, NF}' \
<<EOF
foo;bar;baz
;
10;20;30
EOF
```
