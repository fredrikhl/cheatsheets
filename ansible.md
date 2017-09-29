# ansible

```bash
ansible "<host-selection>" -m <module> -a "<module-args>"
```


## Host-selection

```
example.org
sub1.example.org;sub2.example.org
hostgroup
hostgroup;example.org
```


## Examples

```bash
ansible localhost -m command -a "echo 'foo'"
```
