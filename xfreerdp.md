# xfreerdp

## Connection settings

```bash
xfreerdp /d:<domain>
xfreerdp /u:<username>
xfreerdp /v:<host>
```

## Keyboard settings

```bash
xfreerdp /kbd-list        # List keyboard layout codes
xfreerdp /kbd:0x00000414  # Set layout
```

## Appearence

```bash
xfreerdp /monitor-list
xfreedrp /size:1024x768
xfreerdp /t:<title>
xfreerdp -wallpaper -themes +fonts
```

## Behaviour

```bash
xfreerdp +clipboard      # Shared clipboard
xfreerdp -grab-keyboard  # Do not grab global keyboard shortcuts
```

