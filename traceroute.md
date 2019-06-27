# traceroute

## Check TCP connection

```bash
traceroute -T -p <port> <host>
```


## Special flags

- *!num* icmp unreachable code *num*
- *!C* Precedence cutoff in effect
- *!F* Fragmentation needed
- *!H* Host unreachable
- *!N* Network unreachable
- *!P* Protocol unreachable
- *!S* Source route failed
- *!V* Host precedence violation
- *!X* Communication administratively prohibited


## Packet types

- *default* UDP
- *-I* ICMP ECHO
- *-T* TCP SYN
