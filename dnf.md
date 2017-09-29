# To install the latest version of a package:
dnf install <package name>

# To search package details for the given string
dnf search <string>

# To find which package provides a binary
dnf provides <path to binary>

# The following are available after installing "dnf-plugins-core"

# Download a package
dnf download <package name>

# install the build dependencies for a SRPM or from a .spec file
dnf builddep <srpm/.spec file>

# Show package contents
dnf repoquery -l <package name>

# repos

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
