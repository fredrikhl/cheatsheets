# Keytool

Create or manage a java keystore file.

## Make java keystore from PKCS12 keystore

```bash
keytool -importkeystore \
        -scrstoretype PKCS12 \
        -srckeystore <source.p12> \
        -destkeystore <store.jks>
```

## Import a key to a keystore

```bash
keytool -import -keystore <store.jks> -file <cert.pem> -alias <name>
```

## List

```bash
keytool -list
keytool -list <store.jks>
keytool -list -keystore <store.jks>
```
