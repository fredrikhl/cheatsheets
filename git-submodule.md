# git submodule


## clone repo with submodules

```bash
git clone --recursive
```


## fetch submodules in existing repo

```bash
git submodule update --init
```


## Add git submodule

```bash
git submodule add <repo> <subdir>
git submodule init
```


## Update git submodules

```bash
cd <subdir>
git pull [opts]
cd -
git add <subdir>
```


## Revert git submodule

Revert a working-tree change (e.g. updated to lastest master, but that didn't
work well)

```bash
git submodule update <subdir>
```
