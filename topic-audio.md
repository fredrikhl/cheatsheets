Audio stuff
===========

pw-dump
--------
```
# extract a display name for a known "$node"
pw-dump "$node" | jq -r '.[].info.props | .["node.nick"] // .["node.description"]'

# extract a given attribute for all devices.
pw-dump | jq -r '.[].info.props | .["node.nick"] | select (. != null)'
```


pactl
-----
```
# list all sinks
pactl --format=json list sinks | jq -r '.[].name'

# list all sources
pactl --format=json list sources | jq -r '.[].name'
```
