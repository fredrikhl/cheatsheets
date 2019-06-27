# Package contents

## Find package by content

```bash
dnf provides /path/to/file
```


## List package contents

Requires *dnf-plugins-core*?

```bash
dnf repoquery -l <package-name>
```


## Download a package

Requires *dnf-plugins-core*?

```bash
dnf download <package-name>
```


# Versions

## List all verisons

```bash
dnf --showduplicate --release=28 list <package-name>
```


## Install specific version

```bash
dnf install <package-name>-<version>
```


# Repos

## list repos

```bash
dnf repolist [--all|--enabled|--disabled]
```


## list installed packages from given repo

```bash
dnf repo-pkgs <repo> list installed
```


## enable disable repos

```bash
dnf config-manager --set-enabled <repo>
dnf config-manager --set-disabled <repo>
```


# Install build dependencies

Install the build dependencies for a SRPM or from a `.spec` file. Requires
*dnf-plugins-core*?

```bash
dnf builddep <srpm/.spec file>
```
