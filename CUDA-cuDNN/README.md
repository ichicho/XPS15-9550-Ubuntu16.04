# CUDA and cuDNN installation guide
## Install CUDA
Change to text mode(Ctrl+Alt+3) and stop x server.
```
sudo service lightdm stop
```
Download Runfile and **run with _--no-opengl-libs_ flag**
```
chmod +x cuda_*_linux.run
sudo cuda_*_linux.run --no-opengl-libs
```
### Device Node Verification and Post-instnallation
Follow Installation Guide Linux in [guide](https://docs.nvidia.com/cuda/).
## Install patch
Download patch and run it.
```
command for run patch
```
## Install cuDNN
Follow Installing cuDNN on Linux in [guide](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html).

