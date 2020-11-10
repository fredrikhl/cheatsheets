# grub2

## fedora

```bash
# rebuild boot config
grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```

Fix issue with missing/empty grubenv

```bash
# on '/usr/bin/grub2-editenv: error: invalid environment block.'
grub2-editenv create
```
