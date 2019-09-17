# bcc-tools

- `/usr/share/bcc/tools/`
- `/usr/share/bcc/tools/doc/`
- `/usr/share/man/man8/bcc-*`

## sslsniff

```bash
man 8 bcc-sslsniff
/usr/share/bcc/tools/sslsniff -h

# sniff curl commands
/usr/share/bcc/tools/sslsniff -c curl

# sniff process
/usr/share/bcc/tools/sslsniff -p <pid>
```

## statsnoop

```bash
man 8 bcc-statsnoop
/usr/share/bcc/tools/sslsniff -h

# Look for access of a specific file
/usr/share/bcc/tools/statsnoop | grep <filename>
```
