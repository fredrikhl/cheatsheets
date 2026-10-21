# firewall-cmd

```bash
# Show zone/interface mapping
firewall-cmd --get-active-zones

# Show zone
firewall-cmd --info-zone=<zone>

# Show all zones w/info
firewall-cmd --list-all-zones
```


## Definitions

```bash
firewall-cmd --get-zones
firewallc-cmd --get-services
firewallc-cmd --get-icmptypes
```


## Logging and debugging

```bash
# enable/disable logging of dropped connections
firewall-cmd --get-log-denied
firewall-cmd --set-log-denied=all
firewall-cmd --set-log-denied=off
```


## Modify zone rules

```bash
firewall-cmd [--permanent] [--zone=<zone>] --add-service=https
firewall-cmd [--permanent] [--zone=<zone>] --add-port=443/tcp
firewall-cmd [--permanent] [--zone=<zone>] --add-source=127.0.0.1/32
```


## Reload/apply changes

*runtime*: Changes are added to the runtime by default, and should take effect
immediately.  Use `firewall-cmd --runtime-to-permanent` to save settings.

*permanent*: Alternatively, changes can be added with `--permanent`, but these
won't take effect immediately, and needs a reload to take effect: `firewall-cmd
--reload`.  Non-permanent changes are wiped on reload
