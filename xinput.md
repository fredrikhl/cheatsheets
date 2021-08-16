# xinput

## list devices

```bash
xinput list
```

## list properties

```bash
xinput list-props <device>
# e.g. mouse
# xinput list-props 10
# xinput list-props 'Generic Mouse'
```

## set property

```bash
xinput set-prop <device> <prop> <value>
# e.g. mouse speed
# xinput set-prop 10 305 -0.5
# xinput set-prop 'Generic Mouse' 'libinput Accel Speed' -0.5
```
