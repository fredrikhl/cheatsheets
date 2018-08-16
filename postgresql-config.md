# Config

```bash
sudo -i -u postgres
cd /var/lib/pgsql/data
```


## `pg_hba.conf`

```
# Format:
#   local      DATABASE  USER  METHOD  [OPTIONS]
#   host       DATABASE  USER  ADDRESS  METHOD  [OPTIONS]
#   hostssl    DATABASE  USER  ADDRESS  METHOD  [OPTIONS]
#   hostnossl  DATABASE  USER  ADDRESS  METHOD  [OPTIONS]
#
# Configure trust (no password) when connecting from localhost, or when
# connecting on file socket
#
local all  all                trust
host  all  all  127.0.0.1/32  trust
host  all  all  ::1/128       trust
#
# Configure ident (no password for given users) on socket connections
# Mappings are defined in `pg_ident.conf`
#
local all  all                ident map=usermap
#
```


## `pg_ident.conf`

```
# Format:
#   MAPNAME  SYSTEM-USERNAME  PG-USERNAME
#
# let `foo` and `bar` connect as `postgres`
#
usermap  foo  postgres
usermap  bar  postgres
#
# trust system-users with same name as postgres-users
#
usermap  /^(.*)$  \1
#
```
