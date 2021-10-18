# Encrypt/decrypt files with OpenSSL

## encrypt

Encrypt a single file:

```bash
openssl enc -aes-256-cbc -e -in <file> -out <file>.enc
cat <file> | openssl enc -aes-256-cbc -e > <file>.enc
```

Create an archive and encrypt:

```bash
tar cz <folder> | openssl enc -aes-256-cbc -e > <folder>.tar.gz.enc
```


## decrypt

Decrypt a single file:

```bash
openssl enc -aes-256-cbc -d -in <file>.enc -out <file>.dec
cat <file>.enc | openssl enc -aes-256-cbc -d > <file>.dec
```

Decrypt and extract an archive:

```bash
openssl enc -aes-256-cbc -d -in <folder>.tar.gz.enc | tar xz
```


## base64

To add base64-encoding/decoding, use `-a`.
