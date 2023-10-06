# httpie

## Basic request

```
http example.org/api/foo
http :8080/api/foo
http localhost:3000/api/foo
http DELETE :8080/groups/foo
```


## Connect

Defaults to http, and localhost:80.  Only host/port portion needs to be given to
override:

```
http :8080          # http://localhost:8080
http example.org:   # http://example.org:80
http :/foo          # http://localhost:80/foo
```

If scheme is given, the full URL needs to be given


## Request body

JSON by default:

```bash
http PUT :8080/users/AzureDiamond password=hunter2
http [POST] :8080/auth/login username=AzureDiamond password=hunter2
http :8080/gauge/my-gauge value:=10 replace:=true
```

- Use `:=` for non-string values
- Use `--form` to send www-form-urlencoded body


## Headers

```bash
http :8080/api/foo X-Api-Key:secret Accept-Language:en
```


## Session

```bash
http --session=myname :8080/auth/login username=AzureDiamond password=hunter2
http --session=myname :8080/me/user-info
```

Sessions are stored in `http --debug 2>&1 | grep config_dir`


## Verbosity

`-p`, `--print` to select that to print:

- `H` - request headers
- `B` - request body
- `h` - response headers
- `b` - response body
- `m` - metadata

`--all` to include redirect request/response output

`-v` == `--all --print HBhb`
`-vv` == `--all --print HBhbm`


```
http -p HBhb :8080/auth/login username=AzureDiamond password=hunter2
```
