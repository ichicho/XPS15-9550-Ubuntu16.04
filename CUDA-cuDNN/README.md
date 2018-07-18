# CUDA and cuDNN installation guide
## Install CUDA
1.Download the Runfile for installation from NVIDIA.

2.Change to text mode(Ctrl+Alt+3) and stop x server.
```
sudo service lightdm stop
```
3.Run the Runfile **with _--no-opengl-libs_ flag**. (OpenGL will break GUI in NVIDIA Optimus technology-based laptop.)
```
chmod +x cuda_*_linux.run
sudo cuda_*_linux.run --no-opengl-libs
```
### Device Node Verification and Post-instnallation
Follow *Installation Guide Linux* in [official guide](https://docs.nvidia.com/cuda/).
## Install patch
Download patch and run it.
```
chmod +x cuda_*_linux.run
sudo cuda_*_linux.run
```
## Install cuDNN
Follow *Installing cuDNN on Linux* in [official guide](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html).

Path may differ from the official guide. Change it properly.
