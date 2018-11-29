# Logical Volume Manager


## Status

```bash
# List physical volumes
pvs

# List volume groups and sizes
vgs

# List logival volumes
lvs
```


## Create a volume group

```bash
lvcreate -L 4G -n <lv> <vg>
```

```bash
# format /dev/<vg>/<lv>, eg:
mkfs.<fs> /dev/<vg>/<lv>
# mount
mkdir -p <dir>
mount /dev/<vg>/<lv> <dir>
# add to fstab
echo "/dev/mapper/<vg>-<lv> <dir> <fs> defaults 1 1 >> /etc/fstab
```


## Extend a volume group

```bash
# resize in byte units
lvextend -L +1G <lv>
```

```bash
# resize relative to size
lvextend -l 80%FREE
```

```bash
# resize file system
lvextend -L +10G /dev/internvg/root
resize2fs /dev/internvg/root
```


## Don't know what this is, but I had it pasted for some reason..

    Exclusive Activation of a Volume Group in a Cluster 
    Link --> https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/High_Availability_Add-On_Administration/s1-exclusiveactive-HAAA.html 
    1> vgs --noheadings -o vg_name
    2> volume_list = [ "rhel_root", "rhel_home" ]
    3> dracut -H -f /boot/initramfs-$(uname -r).img $(uname -r)
    4> Reboot the node
    5> uname -r to verify the correct initrd image

