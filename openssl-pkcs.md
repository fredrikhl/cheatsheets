# openssl pkcs7


```bash
# print/convert certs
openssl pkcs7 -inform DER -in <file.p7b> -print_certs
```


# openssl pkcs12

Extract PEM-files

```
openssl pkcs12 -in <file.p12> -cacerts -nokeys [-legacy] -out cacert.pem
openssl pkcs12 -in <file.p12> -clcerts -nokeys [-legacy] -out cert.pem
openssl pkcs12 -in <file.p12> -nocerts -noenc [-legacy] -out key.pem
```
