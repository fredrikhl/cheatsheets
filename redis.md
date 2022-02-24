# redis-cli

```bash
# connect to database with interactive shell
redis-cli [-h localhost] [-p 6379] [-n 0]

# run a specific command
redis-cli KEYS '*'
redis-cli --raw LRANGE foo 0 1
```

## Connect to database

- Authenticate: `AUTH <key>`
- Select database index: `SELECT <n>`

## Inspect a database

- List info on databases: `INFO [item]`, `INFO keyspace`
- List out keys in database: `KEYS <pattern>`
- Get value type on key: `TYPE <key>`
- Get ttl on key: `TTL <key>`


## Types

### Scalar

content of `<key>`:

```redis
GET <key>
```


### List

length of `<key>`:
```redis
LLEN <key>
```

get list contents of `<key>`
```redis
LRANGE <key> <start> <stop>
```


### Set

size of `<key>`:
```redis
SCARD key
```

get items in set `<key>`
```redis
SMEMBERS key
```
