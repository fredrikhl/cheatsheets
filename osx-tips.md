# Useful OSX cheats

## disable osx turds on external drives

```bash
# Prevent from using trash
touch /Volumes/<drive>/.Trashes

# Prevent from using fstab-logging
touch /Volumes/<drive>/.fseventd/no_log

# Prevent from spotlight-indexing
touch /Volumes/<drive>/.metadata_never_index
```


## NFSv4

```
#/etc/nfs.conf
#
# nfs.conf: the NFS configuration file
#
nfs.client.mount.options = vers=4
```


## lsregister

```bash
alias lsregister='/System/Library/Frameworks/CoreServices.framework/Versions/Current/Frameworks/LaunchServices.framework/Support/lsregister'

# Reset 'Open With...' contextual menu
lsregister -kill -r -domain local -domain system -domain user
```


## sysctl

```bash

# list
sysctl -a

# get
sysctl <setting>

# search
sysctl -r <pattern>

# set
sysctl -w <setting>=<value>
```

To make changes permanent:

```
# /etc/sysctl.conf
#
<setting>=<value>
```

```bash
# max sockets
sysctl -w kern.ipc.somaxconn=2048

# max open files
sysctl -w kern.maxfiles=4096
sysctl -w kern.maxfilesperproc=1024
```
