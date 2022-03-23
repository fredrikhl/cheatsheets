# sops

## Basics

```bash
# edit a file
sops <encrypted.yaml>

# decrypt a file
sops -d <encrypted.yaml>

# encrypt a file inplace
sops -e -i [encrypt-opts] <plaintext.yaml>
```


## Encrypt a file using vault transit key

```bash
export VAULT_ADDR=https://vault.example.org:8200
KEY=<store>/keys/<name>
vault login <args>
sops -e -i --hc-vault-transit "${VAULT_ADDR}/v1/${KEY}" secrets.yaml
```
