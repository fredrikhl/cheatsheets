# OpenSSL

## dhparam
Generate Diffie-Hellman parameters:
```bash
openssl dhparam -outform PEM -out dhparams.pem 2048
```

## ocsp
Print request and response:
```bash
openssl ocsp -issuer <chain.pem> \
             -cert <cert.pem> \
             -text \
             -url <ocsp-url> \
             -header Host <ocsp-hostname>
```


## check if key matches cert

```bash
# certificate
openssl x509 -noout -modulus -in <cert> | openssl md5

# key
openssl rsa -noout -modulus -in <key> | openssl md5

# certificate request
openssl req -noout -modulus -in <csr> | openssl md5
```
