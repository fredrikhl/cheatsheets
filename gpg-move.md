# Move GPG keys and data

## Export keys

```bash
# export all public keys
gpg -a --export > gpg-all-pubkeys.asc

# export a specific public key
gpg -a --export [key-id] > gpg-my-pubkey.asc

# export all secret keys
gpg -a --export-secret-keys > gpg-all-seckeys.asc

# export a specific secret key
gpg -a --export-secret-keys [key-id] > gpg-my-seckey.asc
```


## Import keys

```bash
# import public/secret keys
gpg --import keys.asc
```


## Export/import trust

```bash
# export trust settings
gpg --export-ownertrust > keytrust.txt

# import trust settings
gpg --import-ownertrust keytrust.txt
```
