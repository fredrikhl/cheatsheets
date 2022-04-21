# apt

```bash
# search for package
apt search package

# show package info
apt show package
```


## add/remove

```bash
# add
apt install package [package...]

# remove
apt remove package [package...]
```


## update

```bash
# update package lists
apt update

# list pending upgrades
apt list --upgradable

# update pending
apt upgrade

# download and install all update and new dependencies
apt dist-upgrade
```
