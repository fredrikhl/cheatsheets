# rpm

```bash
# To install a package:
rpm -ivh <rpm>

# To remove a package:
rpm -e <package>

# To remove a package, but not its dependencies
rpm -e --nodeps <package>

# Display checksum against source
rpm -K <package>

# Verify a package
rpm -V <package>
```


## Dependencies

```bash
# List dependencies of RPM-file
rpm -qR -p <file>

# List dependencies of package
rpm -qR <installed-package>

# Find missing dependencies for an RPM-file
rpm -i --test <file>

# Find installed packages that depends on a package
rpm -q --whatrequires <installed-package|file>
```


## Package content

```bash
# To find what package installs a file:
rpm -qf </path/to/file>

# To find what files are installed by a package:
rpm -ql <installed-package>
rpm -ql -p <file>
```

```bash
# extract content
mkdir <rpm-content>
rpm2cpio </path/to.rpm> | cpio -idmv -D <rpm-content> --no-absolute-filenames
```

## Specific files

```
# To find what package owns a file
rpm -qf <file>

# To find what package provides a file
rpm -q --whatprovides <file>
```


## Finding packages

```bash

# To list all installed packages:
rpm -qa

# list installed packages by size
rpm -qa --queryformat '%{name} %{size}\n' | sort -n -k 2 -r | head -n 20
```
