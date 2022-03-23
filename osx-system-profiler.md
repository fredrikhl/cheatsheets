# system_profiler


## Liste ut apps

```bash
/usr/sbin/system_profiler SPApplicationsDataType
```

Liste ut 32-bits apps

```bash
/usr/sbin/system_profiler SPApplicationsDataType | grep -A3 "64-Bit (Intel): No"| grep Location | cut -c17-
```


## Finne serienummer

```bash
system_profiler SPHardwareDataType | grep Serial
```
