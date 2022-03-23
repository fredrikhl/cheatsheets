# httpie

## Basic request

```
http example.org/api/foo
http :8080/api/foo
http localhost:3000/api/foo
http DELETE :8080/groups/foo
```


## application/json

```bash
http PUT :8080/users/AzureDiamond password=hunter2
http [POST] :8080/auth/login username=AzureDiamond password=hunter2
```


## Headers

```bash
http :8080/api/foo X-Api-Key:secret Accept-Language:en
```


## Session

```bash
http --session=myname :8080/auth/login username=AzureDiamond password=hunter2
http --session=myname :8080/me/user-info
```
