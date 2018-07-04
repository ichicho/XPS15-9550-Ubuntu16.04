# XPS15-9550-Ubuntu16.04
Something important during installation of Ubuntu16.04 on XPS15 9550.

## configure NVIDIA Geforce GTX 960m driver
**Update Intel microcode and reboot**
```
sudo apt-get update
sudo apt-get install intel-microcode
```
**Disable nouveau driver**
Check status of nouveau
```
lsmod | grep nouveau
```
If there is a output, nouveau driver is working and you should do the following.

Else, Disabling nouveau driver is not needed.

Write following contents in `etc/modprobe.d/blacklist-nouveau.conf` as root:
```
blacklist nouveau
options nouveau modeset=0
```

Restart kernel initramfs and reboot
```
sudo update-initramfs -u
reboot
```

Check status of nouveau
```
lsmod | grep nouveau
```
If there is no output, it means nouveau driver is successfully disabled.

**Install NVIDIA driver**
Until 2018.7.4 is 390, stable version is 390.

Change to text mode(Ctrl+Alt+3) and stop x server

`sudo service lightdm stop`

Option 1: install from ppa
