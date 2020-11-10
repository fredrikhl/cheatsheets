# notify-send

Send dbus notifications using `org.freedesktop.Notifications.Notify`

```

  notify-send [OPTION…] <SUMMARY> [BODY]

  -u, --urgency=LEVEL               Specifies the urgency level (low, normal, critical).
  -t, --expire-time=TIME            Specifies the timeout in milliseconds at which to expire the notification.
  -a, --app-name=APP_NAME           Specifies the app name for the icon
  -i, --icon=ICON[,ICON...]         Specifies an icon filename or stock icon to display.
  -c, --category=TYPE[,TYPE...]     Specifies the notification category.
  -h, --hint=TYPE:NAME:VALUE        Specifies basic extra data to pass. Valid types are int, double, string and byte.
```

## Basic notifications

```
notify-send "only summary"
notify-send "summary and body" "This is a test notification a summary and a body"
```


## Urgency

```bash
notify-send -u critical 'Important!'
notify-send -u normal 'Message'
notify-send -u low 'Not important...'
```


## Expire

```
notify-send 'no timeout' 'this is the default'
notify-send -t 1000 'timeout=1s'
notify-send -t 10000 'timeout=10s'
```


## Application name

```bash
notify-send -a 'my-appname' 'my-header'
```


## Icons

```bash
notify-send -i 'audio-volume-medium' 'Volume'
notify-send -i '/usr/share/icons/gnome/48x48/status/audio-volume-medium.png' 'Volume'
```


## Category

```bash
notify-send -c email.arrived "You've got mail!"
notify-send -c 'device.removed,network.disconnected' 'Offline!'
```


## Hints

```bash
# positioning hints
notify-send -h 'int:x:100' -h 'int:y:100' 'position 100,100'

# progress hints
notify-send -h 'int:value:50' 'current value: 50'

# desktop-entry hints
notify-send -h "string:desktop-entry:firefox" "desktop-entry: firefox"
```
