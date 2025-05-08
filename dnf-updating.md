# DNF update utils

## Install updates

```bash
dnf upgrade --refresh
```


## Check if updates needs restart

```bash
dnf install dnf-utils
dnf needs-restarting
```


## List outdated packages

```bash
# List of outdated packages
dnf updateinfo --quiet --updates --list

# Number of outdated packages
dnf updateinfo --quiet --updates --list | wc -l | sed -e 's/^0$//'
```


## Upgrade major version

```bash
dnf install dnf-plugin-system-upgrade
dnf system-upgrade download --releasever=<version> [--allowerasing] [--best]
dnf system-upgrade reboot
```


## Automatic package cache update

Eliminate the need for using `dnf --refresh`, and waiting for the refresh on
various `dnf` commands.

```bash
systemctl enable dnf-makecache.timer
systemctl start dnf-makecache.timer
```
