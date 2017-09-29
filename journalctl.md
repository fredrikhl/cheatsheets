# journalctl


## Filter by log level

`journalctl -p <level>`, where `<level>` is one of:

0. emerg
1. alert
2. crit
3. err
4. warning
5. notice
6. info
7. debug


## Useful options

```bash
journalctl -f  # Follow output
journalctl -b  # Show log entries since boot
```


## Filters

```bash
journalctl _PID=1200                    # Filter by process ID
journalctl _UID=1000                    # Filter by user ID
journalctl _COMM=sshd                   # Filter by command
journalctl _SYSTEMD_UNIT=tomcat.service # Filter by systemd service (also `-u')
```

List available values for a given filter:

```bash
journalctl -F _PID
```


## Filter by time period

```bash
journalctl --since=2012-10-15 --until="2012-10-16 23:59:59"
journalctl --since="10:00" --until="11:00"
```


## Filter by specific unit

```bash
journalctl -u dbus
journalctl --unit tomcat.service
```


## Arguments

```bash
# filter by executeable name
journalctl /usr/bin/dbus-daemon

# show logs of kernel device nodes
journalctl /dev/sda
```


## Combine filters

```bash
# Logical AND
journalctl _SYSTEMD_UNIT=avahi-daemon.service _PID=28097

# Using the same field twice makes it a logical OR
journalctl _SYSTEMD_UNIT=avahi-daemon.service _SYSTEMD_UNIT=dbus.service

# Use `+' as logical OR
journalctl _SYSTEMD_UNIT=avahi-daemon.service _PID=28097 + _SYSTEMD_UNIT=dbus.service
```
