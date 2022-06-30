# dmidecode

Dump DMI table data.  Run as `root`.

```bash
dmidecode
dmidecode -s <keyword>
dmidecode -t <type>
dmidecode --oem-sring <n>
```


## keywords

- bios-vendor
- bios-version
- bios-release-date
- bios-revision
- firmware-revision
- system-manufacturer
- system-product-name
- system-version
- system-serial-number
- system-uuid
- system-sku-number
- system-family
- baseboard-manufacturer
- baseboard-product-name
- baseboard-version
- baseboard-serial-number
- baseboard-asset-tag
- chassis-manufacturer
- chassis-type
- chassis-version
- chassis-serial-number
- chassis-asset-tag
- processor-family
- processor-manufacturer
- processor-version
- processor-frequency


## types

- baseboard
- bios
- cache
- chassis
- connector
- memory
- processor
- slot
- system


## examples

```bash
# get model number, serial number
sudo dmidecode -t system
```
