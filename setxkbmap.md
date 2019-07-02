# setxkbmap

```bash
setxkbmap -layout <layout> [-variant <variant>]
```


## Layouts

List layouts:

```
# Layouts
localectl list-x11-keymap-layouts

# Variants
localectl list-x11-keymap-variants [layout]
```


## Layout per device

```bash
# List device IDs
xinput -list

# Set layout for device
setxkbmap -device <id> ...
```


## xkb layout files

Default layouts are located in:

- `/usr/share/X11/xkb/symbols/`
