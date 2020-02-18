# Install-experiment-environment
Install tutorial(graphic driver(rtx2080ti), cuda 10.2, cudnn)

RTX 2080ti Graphic Driver Install
=========
1. Check if there is an existing Graphic driver installed.
```bash
# cat /proc/driver/nvidia/version   
cat: /proc/driver/nvidia/version: No such file or directory   

```

2. Check for compatible Graphic Drivers
```bash
# ubuntu-drivers devices

== /sys/devices/pci0000:00/0000:00:01.1/0000:02:00.0 ==   
modalias : pci:v000010DEd00001E02sv000010DEsd000012A3bc03sc00i00   
vendor   : NVIDIA Corporation   
manual_install: True   
driver   : nvidia-driver-435 - distro non-free   
driver   : nvidia-driver-440 - third-party free recommended   
driver   : nvidia-driver-415 - third-party free   
driver   : xserver-xorg-video-nouveau - distro free builtin   

```
recommended driver is nvidia-driver-440
so Download the driver for your version.
Download [Link](https://www.nvidia.co.kr/Download/driverResults.aspx/156786/kr)
file name is "NVIDIA-Linux-x86_64-440.59.run"

3. Install 

Press ctrl+alt+f2 on the login screen
Enter the ID/PWD

```bash
# cd Download
# chmod +x ./NVIDIA-Linux-x86_64-440.59.run
# sudo sh ./NVIDIA-Linux-x86_64-440.59.run

```
Install!!!!!!

4. Confirm installation
```bash
# nvidia-smi

```



CUDA 10.2 Install
=========
## CUDA 10.2 Install

OS : ubuntu 18.04   
CUDA / CUDNN : 10.0 / 7.6   
Tensorflow Version : 1.14 or 2.0   
GPU : Geforce RTX 2080ti   


## CUDNN Install

Train data : 26 images   
Validation data : 3 images   
ground truth : json file   

 


