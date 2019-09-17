# setxkbmap

```bash
setxkbmap -layout <layout> [-variant <variant>]
```

## Layouts

List layouts:

```bash
# Layouts
localectl list-x11-keymap-layouts

# Variants
localectl list-x11-keymap-variants [layout]
```

Default layouts are located in `/usr/share/X11/xkb/symbols/`


## Per device settings

```bash
# List device IDs
xinput -list

# Set layout for device
setxkbmap -device <id> ...
```

## Options

```bash
setxkbmap -option <option>
```

- Compose: `-option compose:menu`
- ISO Level3: `-option level3:ralt_switch`
