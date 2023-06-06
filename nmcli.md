# nmcli


## wifi

```
# Desc: Command line interface to NetworkManager

# Connect to a wireless access point - Parameters:
# 	<wiface> -- the name of your wireless interface
#	<ssid> -- the SSID of the access point
#	<pass> -- the WiFi password
nmcli d wifi connect <ssid> password <pass> iface <wiface>

# Disconnect from WiFi - Parameters:
#	<wiface> -- the name of your wireless interface
nmcli d wifi disconnect iface <wiface>

# Get WiFi status (enabled / disabled)
nmcli radio wifi

# Enable / Disable WiFi
nmcli radio wifi <on|off>

# Show all available WiFi access points
nmcli dev wifi list

# Refresh the available WiFi connection list
nmcli dev wifi rescan
```


## show

```
# show available connections
nmcli con [show]

# show active connections
nmcli con show --active

# show settings for a connection
nmcli con show <interface>

# show devices
nmcli dev [status]

# list config files/sources
nmcli -f TYPE,FILENAME,NAME con
```

# Add a dynamic ethernet connection - parameters:
#	<name> -- the name of the connection
#	<iface_name> -- the name of the interface
ncmli con add type ethernet con-name <name> ifname <iface_name>

# Bring up the ethernet connection
nmcli con up <name>
