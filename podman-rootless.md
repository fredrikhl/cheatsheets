# Rootless podman setup


See
<https://github.com/containers/podman/blob/main/docs/tutorials/rootless_tutorial.md>
for more tips.


## Install

```bash
dnf install podman fuse-overlayfs slirp4netns podman-compose podman-plugins
```


## subuid/subgid setup

Add subuid/subgid ranges:

```
sudo usermod --add-subuids 1000000-165535 --add-subgids 1000000-165535 "$USER"
```


Verify that it was added

```
grep "$USER" /etc/subuid /etc/subgid
/etc/subuid:<brukernavn>:1000000:65536
/etc/subgid:<brukernavn>:1000000:65536
```


Make sure podman knows it was added:

```
podman system migrate
```
