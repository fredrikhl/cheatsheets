# SSH config


## ControlMaster

```
host *
    Compression yes
    ControlMaster auto
    ControlPath ${XDG_RUNTIME_DIR}/ssh/control-master/ssh-%r@%h:%p
    ServerAliveInterval 10
```


## ProxyJump

```
host mgmt
    # select management host
    Hostname my-mgmt-host.example.org

host real-host.example.org real-host
    Hostname real-host.example.org
    ProxyJump mgmt
```


## Keys

```
    AddKeysToAgent yes
    IdentityFile ~/.ssh/id-fhl-drift
    IdentitiesOnly yes
    User fhl-drift
```
