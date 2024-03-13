# usermod

Part of shadow-utils.  Other relevant commands: `useradd`, `userdel`,
`groupadd`, `groupmod`, `groupdel`.


## Add user to a group

```bash
usermod -a -G <group name> <username>
```


## Use group

Log into the group to avoid having to log out/in.

```bash
newgrp <group name>
```
