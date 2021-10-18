# OpenSSL as a certificate tool


## View certificate

```bash
openssl x509 -noout -text -in cert.pem

# SHA-1 Fingerprint
openssl x509 -noout -sha1 -fingerprint cert.pem
```

### View OCSP-info

```bash
openssl x509 -noout -ocspid -in cert.pem
openssl x509 -noout -ocsp_url -in cert.pem
```


## Create a certificate request

```bash
# SSH-cert
openssl req -newkey rsa:2048 -x509 -days 3560 -keyout new.key -out new.cert

# Genrerate certificate request
openssl req -new -key new.key -out new.csr

# Generate self-signed cert
openssl req -new -nodes -x509 -extensions v3_ca -subj "/C=NO/O=USIT/CN=hostname" -days 9000 -keyout new.key -out new.pem
```


### Make a csr

request.cnf
```
[ req ]
default_bits = 2048
prompt = no
encrypt_key = no
default_md = sha256
distinguished_name = dn
utf8 = yes
req_extensions = v3_req

[ v3_req ]
basicConstraints = CA:FALSE
keyUsage = nonRepudiation, digitalSignature, keyEncipherment
subjectAltName = @alt_names

[ dn ]
C = NO
L = City/Location
O = Organization
OU = OrganizationalUnit
CN = example.org

[alt_names]
DNS.0 = example.org
DNS.1 = *.example.org
DNS.2 = *.*.example.org
DNS.3 = localhost
```

Make key and csr from cnf:
```
openssl req -new -nodes -keyout <new.key> -out <request.csr> -config <request.cnf>
```

View csr:
```bash
openssl req -text -noout -verify -in new.csr
```


### Sign certificate request

```bash
openssl x509 -req -days 365 -in <request.csr> -signkey <ca_key.key> -out signed.crt
```
