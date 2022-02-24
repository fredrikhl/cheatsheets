# Loops


```bash
# s1, s2
for item in s1 s2; do echo "$item"; done;
```


## Range and combinations

```bash
# 1, 2, …, 10
for i in {1..10}; do echo "$i"; done

# 1, 3, …, 9
for i in {1..10..2}; do echo "$i"; done

# foo01, foo02, foo07
for s in foo0{1,2,7}; do echo "$s"; done

# dx1, dx2, dx3, dy1, dy2, dy3
for s in d{x,y}{1..3}; do echo "$s"; done
```


## Arrays

```bash
declare -a my_list=( foo bar baz )
# declare -A my_list=( [a]="foo" [b]=bar [c]=baz )

# iterate over array values
for item in "${my_list[@]}"; do echo "$item"; done;

# iterate over array indices (or associative array keys)
for i in "${!my_list[@]}"; do echo "$i - ${my_list[$i]}"; done;
```


## for loop

```bash
for (( i=0; i < 5; i++ )); do echo "$i"; done;
```
