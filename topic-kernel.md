# Linux kernel stuff

## kernel modules

```
# list loaded modules
lsmod

# load a module into kernel
modprobe modulename

# remove a module from kernel
modprobe -r modulename
```

## kernel ring buffer

```
dmesg

# only kernel messages
dmesg --kernel
```
