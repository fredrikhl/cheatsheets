# `nsswitch.conf`

Auths and authz on Linux.


## `passwd: compat`

Users in `/etc/passwd` can authenticate.  For LDAP-users:


```
+username
@netgroup
```


## `passwd: files sss`


- `/etc/security/access.conf`
- `/etc/security/access.d/<name>.conf`

```
+: <subject> [subject...] : <source> [source...]
```

Where *subject* is a username or netgroup:

- `username`
- `@netgroup`

And *subject* is a network location:

- `ALL`
- `LOCAL`
- `129.240.0.0/16`
- `2001:700:100::/40`
