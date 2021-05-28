# openssl verify

Check certificates with `openssl`


```bash
openssl verify -CAfile root.pem intermediate.pem
```

```bash
openssl verify -CAfile intermediate.pem -partial_chain cert.pem
```
