# git clone

```bash
git clone <repo> [dest]
```


Checkout a given, non-default branch name:

```bash
git clone --branch=<name>
```

Omit branches, i.e. only fetch commits/history/objects in the checkout branch:

```bash
git clone --single-branch
```

Omit tags:

```bash
git clone --no-tags
```

Truncate history with `--depth=<n>` to replace old commits with one, big grafted
parent commit that shows the state at `HEAD~<n>`:

```bash
git clone --depth=<n>
```
