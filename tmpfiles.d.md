# tmpfiles.d

```bash
man tmpfiles.d
man systemd-tmpfiles
```


## Initialize

```bash
systemd-tmpfiles --user [--dry-run] --create
```


## User config

```
~/.config/user-tmpfiles.d/*.conf
~/.local/share/user-tmpfiles.d/*.conf
```


## Config format

```
#Type Path                                     Mode User Group Age         Argument

f     /file/to/create                          mode user group -           content
f+    /file/to/create-or-truncate              mode user group -           content
w     /file/to/write-to                        -    -    -     -           content
w+    /file/to/append-to                       -    -    -     -           content
d     /directory/to/create-and-clean-up        mode user group cleanup-age -
D     /directory/to/create-and-remove          mode user group cleanup-age -
e     /directory/to/clean-up                   mode user group cleanup-age -
v     /subvolume-or-directory/to/create        mode user group cleanup-age -
q     /subvolume-or-directory/to/create        mode user group cleanup-age -
Q     /subvolume-or-directory/to/create        mode user group cleanup-age -
p     /fifo/to/create                          mode user group -           -
p+    /fifo/to/[re]create                      mode user group -           -
L     /symlink/to/create                       -    -    -     -           symlink/target/path
L+    /symlink/to/[re]create                   -    -    -     -           symlink/target/path
c     /dev/char-device-to-create               mode user group -           major:minor
c+    /dev/char-device-to-[re]create           mode user group -           major:minor
b     /dev/block-device-to-create              mode user group -           major:minor
b+    /dev/block-device-to-[re]create          mode user group -           major:minor
C     /target/to/create                        -    -    -     cleanup-age /source/to/copy
C+    /target/to/create                        -    -    -     cleanup-age /source/to/copy
x     /path-or-glob/to/ignore/recursively      -    -    -     cleanup-age -
X     /path-or-glob/to/ignore                  -    -    -     cleanup-age -
r     /path-or-glob/to/remove                  -    -    -     -           -
R     /path-or-glob/to/remove/recursively      -    -    -     -           -
z     /path-or-glob/to/adjust/mode             mode user group -           -
Z     /path-or-glob/to/adjust/mode/recursively mode user group -           -
t     /path-or-glob/to/set/xattrs              -    -    -     -           xattrs
T     /path-or-glob/to/set/xattrs/recursively  -    -    -     -           xattrs
h     /path-or-glob/to/set/attrs               -    -    -     -           file attrs
H     /path-or-glob/to/set/attrs/recursively   -    -    -     -           file attrs
a     /path-or-glob/to/set/acls                -    -    -     -           POSIX ACLs
a+    /path-or-glob/to/append/acls             -    -    -     -           POSIX ACLs
A     /path-or-glob/to/set/acls/recursively    -    -    -     -           POSIX ACLs
A+    /path-or-glob/to/append/acls/recursively -    -    -     -           POSIX ACLs
```
