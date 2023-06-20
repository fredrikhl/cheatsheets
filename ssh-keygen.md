# ssh-keygen

Create or modify SSH keys.


## Generate key

```bash
# Generate a 4096-bit RSA-key:
ssh-keygen -t rsa -b 4096

# Generate an ed25519-key:
ssh-keygen -t ed25519

# Generate key with a given comment
ssh-keygen -t ed25519 -C "${USER}@${HOSTNAME}

# Generate key with a given passphrase
ssh-keygen -t ed25519 -P passphrase

# Write key to specific location
ssh-keygen -t ed25519 -f ~/.ssh/my-key
```


## Modify passphrase

```bash
# To set or update a passphrase on a key
ssh-keygen -p -P <old pass> -N <new pass> -f "${HOME}/.ssh/my_key"

# To remove passphrase on a key
ssh-keygen -p -P <old pass> -N '' -f "${HOME}/.ssh/my_key"
```


## Modify comment

```bash
ssh-keygen -c -C "foo" -f "${HOME}/ssh/id_rsa"
```


## Show fingerprints

```bash
ssh-keygen -lf "${HOME}/.ssh/id_rsa"
ssh-keygen -lf "${HOME}/.ssh/id_rsa.pub"
ssh-keygen -lf "${HOME}/.ssh/authorized_keys"
```
