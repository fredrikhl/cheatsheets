# ansible

Ansible template setup and cheat sheet.

## ansible.cfg

Ansible configuration.

```
[defaults]
inventory = inventory.cfg

[privilege_escalation]
become = True

[ssh_connection]
ssh_args = -o ControlMaster=auto -o ControlPersist=60s -F ssh-config
```

## inventory.cfg

Host inventory and host configuration.

```
# inventory.cfg
host1 ansible_host=127.0.0.1   hostvar=bar
host2 ansible_host=127.0.0.2   hostvar=foo
host3 ansible_host=127.0.0.3   hostvar=bar

[cluster]
host1
host2
host3

[managers]
host1

[nodes]
host2
host3

[cluster:vars]
cluster_name=mycluster

[managers:vars]
mgr=yes

[nodes:vars]
mgr=no

[all:children]
cluster

[all:vars]
ansible_ssh_user=centos
ansible_python_interpreter=/usr/bin/python
```


## ssh-config

Move ssh config to a separate file. That way it's usable with `ssh -F
ssh-config` for connecting to individual nodes as well.

```
# ssh-config

Host *
    UserKnownHostsFile /dev/null
    StrictHostKeyChecking no
    PasswordAuthentication no
    IdentitiesOnly yes
    LogLevel FATAL
```
