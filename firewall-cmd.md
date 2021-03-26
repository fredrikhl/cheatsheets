# firewall-cmd


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
