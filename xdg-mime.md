# xdg-mime


## query

Ask about mime-types and default apps.

```bash
# show mime-type for a given file
xdg-mime query filetype <file>

# show default app for a given mime-type
xdg-mime query default <mime-type>

# show default app for a given file
xdg-mime query default "$(xdg-mime query filetype <file>)"
```


## default

```bash
xdg-mime default <app> <mime-type>
```


## notes

Apps are located in `${XDG_DATA_DIRS}/applications/`

```bash
echo $XDG_DATA_DIRS | sed -e 's,/\?:,/applications/\n,g' | uniq
```

User defaults are stored in `${XDG_CONFIG_HOME}/mimeapps.list`
