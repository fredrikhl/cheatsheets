# xmlsec1

## Check SAML Response XML

Make xml from response:

```bash
xsel -b | base64 -d > <response.xml>
```

```bash
xmlsec1 --verify --pubkey-cert-pem <ca.pem> --id-attr:ID Response <response.xml>
```

```bash
xmlsec1 --verify --pubkey-cert-pem <ca.pem> --id-attr:ID "urn:oasis:names:tc:SAML:2.0:protocol:Response" <response.xml>
```

```bash
xmlsec1 --verify --pubkey-cert-pem <ca.pem> --id-attr:ID "urn:oasis:names:tc:SAML:2.0:assertion:Assertion" --node-xpath /samlp:Response/saml:Assertion <response.xml>
```
