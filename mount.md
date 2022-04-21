# mount

```bash
# To mount / partition as read-write in repair mode:
mount -o remount,rw /

# Bind mount path to a second location
mount --bind /origin/path /destination/path

# To mount Usb disk as user writable:
mount -o uid=username,gid=usergroup /dev/sdx /mnt/xxx

# To mount a remote NFS directory
mount -t nfs example.com:/remote/example/dir /local/example/dir

# To mount an ISO
mount -o loop disk1.iso /mnt/disk
```


## NFS mounts

### Fix buggy NFS share

```bash
mount -o remount /uio/kant/usit-uait-u1
```


### List exports

```bash
showmount -e kant
```
