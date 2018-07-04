# Fix Bluetooth
Because Bluetooth adapter cannot be configured normally by default, some other step should be taken.
## Add firmware
Download [BCM-0a5c-6410.hcd](./BCM-0a5c-6410.hcd) in this repository  and copy it to `/lib/firmware/brcm`.
```
sudo cp BCM-0a5c-6410.hcd /lib/firmware/brcm
```
Credit to [this post](https://bbs.archlinux.org/viewtopic.php?id=204739).
## Fix MX Master
Follow [this](./MX-Master-Fix.md)
