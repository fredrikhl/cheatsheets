# ip

Interfaces
----------
```
# enable/disable interface (e.g. wi-fi)
ip link set dev wlan0 {up|down}

# change mac address 
ip link set dev eth0 address aa:bb:cc:dd:ee:ff

# set a static ip and netmask
ip addr add 192.168.1.100/32 dev eth0

# remove ip from an interface
ip addr del 192.168.1.100/32 dev eth0

# remove all ips from an interface
ip addr flush dev eth0
```

Routing
-------
```
# add default route via gateway IP
ip route add default via 192.168.1.1

# add specific route via interface
ip route add 192.168.0.0/24 dev eth0
```

Info
----
```
# ip address of all interfaces
ip -brief addr

# display routing
ip route

# view neighbors (using ARP and NDP) 
ip neighbor
```
