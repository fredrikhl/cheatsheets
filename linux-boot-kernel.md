# Linux kernel info


```
# current kernel version
uname -r
#
# kernel that will be used at reboot:
grubby --default-kernel
#
# installed kernels (rpm):
rpm -q kernel
```


## Needs reboot

```
# feroda/centos/rhel
needs-restarting -r
#
# others
cat /var/run/reboot-required
```
