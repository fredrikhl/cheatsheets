# Create SSH keys

```bash
# To generate an SSH key:
ssh-keygen -t rsa

# To generate a 4096-bit SSH key:
ssh-keygen -t rsa -b 4096

# To generate a 4096 bit RSA key with a passphase and comment containing the user and hostname
ssh-keygen -t rsa -b 4096 -C "${USER}@${HOSTNAME}" -P passphrase
```

## Encrypt private key

```bash
# To set or update a passphrase on a key
ssh-keygen -p -P <old pass> -N <new pass> -f "${HOME}/.ssh/my_key"

# To remove passphrase on a key
ssh-keygen -p -P <old pass> -N '' -f "${HOME}/.ssh/my_key"
```

## Show fingerprints

```bash
ssh-keygen -lf "${HOME}/.ssh/id_rsa"
ssh-keygen -lf "${HOME}/.ssh/id_rsa.pub"
ssh-keygen -lf "${HOME}/.ssh/authorized_keys"
```
