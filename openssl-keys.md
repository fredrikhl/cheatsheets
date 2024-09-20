# openssl rsa

Generate an RSA key pair

```bash
openssl genrsa -out private.pem 2048
openssl rsa -in private.pem -pubout -out public.pem
```

Generate an ECDSA/P256 key pair

```bash
openssl ecparam -name secp256k1 -genkey -noout -out private.pem
openssl ec -in ec-secp256k1-priv-key.pem -pubout -out public.pem
```
