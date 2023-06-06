# gpg-connect-agent

Send commands to gpg-agent.


## Reload config

```bash
gpg-connect-agent RELOADAGENT /bye
```


## Fix tty issues

```bash
gpg-connect-agent UPDATESTARTUPTTY /bye
```

TODO: In ssh-config

```
Match host * exec "gpg-connect-agent UPDATESTARTUPTTY /bye"
```
