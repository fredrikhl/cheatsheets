# firewall-cmd

```bash
firewall-cmd --get-zones
firewall-cmd --get-active-zones
firewall-cmd --get-default-zone

firewallc-cmd --get-services
firewallc-cmd --get-icmptypes

# Show everything
firewallc-cmd --list-all-zones
```


## Logging and debugging

```bash
firewall-cmd --get-log-denied
firewall-cmd --set-log-denied=all
firewall-cmd --set-log-denied=off
```


## Modify zone rules

```bash
firewall-cmd --info-zone=<zone>
firewall-cmd [--permanent] [--zone=<zone>] --add-service=https
firewall-cmd [--permanent] [--zone=<zone>] --add-port=443/tcp
firewall-cmd [--permanent] [--zone=<zone>] --add-source=127.0.0.1/32
```


## Reload/apply changes

Changes are added to the runtime by default, and should take effect immediately.
Use `firewall-cmd --runtime-to-permanent` to save settings.

Alternatively, changes can be added with `--permanent`, but these won't take
effect immediately, and needs a reload to take effect: `firewall-cmd --reload`.
Non-permanent changes are wiped on reload


## blocklist

```
# Add blocklist to drop zone
firewall-cmd --permanent --zone=drop --add-source=ipset:my-blocklist

# Create blocklist
firewall-cmd -q --permanent \
    --new-ipset=my-blocklist \
    --type=hash:net \
    --option=family=inet \
    --option=hashsize=4096 \
    --option=maxelem=200000

# Add to list (from file)
firewall-cmd --permanent --ipset=my-blocklist --add-entries-from-file=ip-addr.txt

# Clear list
firewall-cmd --permanent --delete-ipset=my-blocklist
```
