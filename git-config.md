# git config

`git config` cheat sheet.


## usage

```bash
git config [--global] [--get] <key>
git config [--global] [--set] <key> <value>

# Set option on one-off command
git -c <key>=<value> <command>
```


## Options

* `core.editor <path>`:
  Default editor for commit message, etc...
* `core.fileMode <bool>`:
  Report change in file mode (git diff, git status)
* `user.email <str>`
* `user.name <str>`
* `color.ui <bool>`:
  Use colors in output?
* `credential.username <str>`
* `remote.origin.url <url>`:
  Push/pull url for remote "origin"


## make remote tracking branch the default push branch:
```bash
git config push.default tracking
git config --global push.default tracking  # Make the setting global
```
