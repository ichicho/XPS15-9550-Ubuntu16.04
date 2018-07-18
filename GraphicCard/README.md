# Install NVIDIA Geforce GTX 960m driver
## Update Intel microcode and reboot
```
sudo apt-get update
sudo apt-get install intel-microcode
```
## Disable nouveau driver
### Check status of nouveau
```
lsmod | grep nouveau
```
If there is a output, nouveau driver is working and you should do the following.

Else, disabling nouveau driver is not needed. This part can be skipped.
### Edit system file
Write following contents in `/etc/modprobe.d/blacklist-nouveau.conf` as root:
```
blacklist nouveau
options nouveau modeset=0
```
Restart kernel initramfs and reboot.
```
sudo update-initramfs -u
reboot
```
### Check status of nouveau
```
lsmod | grep nouveau
```
If there is no output, it means nouveau driver is successfully disabled.
## Install NVIDIA driver
Until 2018.7.4, stable version is 390.

Change to text mode(Ctrl+Alt+3) and stop x server.
```
sudo service lightdm stop
```
### Option 1: install from ppa
```
sudo apt-get purge nvidia-*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
# Take 390 as example:
# sudo apt-get install nvidia-390
sudo apt-get install nvidia-<version>
```
### Option 2: install from NVIDIA
Download Runfile and **run with _--no-opengl-files_ flag**.

OpenGL will make Optimus-based laptop's GUI not work.
```
chmod +x NVIDIA-Linux-x86_64-*.run
sudo NVIDIA-Linux-x86_64-*.run --no-opengl-files
```
### Check whether driver is correctly installed
```
nvidia-smi
```
Information about the graphic card will show if driver is correctly installed.
