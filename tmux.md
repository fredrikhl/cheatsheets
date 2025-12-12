# tmux

## sessions

```bash
# create
tmux new-session -s <session-name>

# attach
tmux attach -t <session-name>

# create or attach
tmux new -s <session-name> || tmux a -t <session-name>

# list sessions
tmux list-sessions
tmux ls
```


- `attach -d`: attach and detach any other sessions
- `attach -r`: attach in read-only mode


## windows/panes

- `<leader> z` - toogle zoom (show current pane only)


## commands

- `list-keys [-T <context>]`, contexts: `prefix`, `root`, …
- `rename-window <title>`
