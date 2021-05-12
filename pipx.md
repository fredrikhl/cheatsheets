# pipx

Install package into a new virtualenv, and link 'apps' (script symlinks in
`.local/bin`).

```bash
pipx install <package>
```


Add an optional package/dependency to an existing package env:

```bash
pipx inject <env> <new-package>

# include script symlinks for the new package
pipx inject --include-apps <env> <new-package>
```
