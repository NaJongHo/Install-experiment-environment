# Install-experiment-environment
Install tutorial(graphic driver(rtx2080ti), cuda 10.2, cudnn) on ubuntu 18.04

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

recommended driver is nvidia-driver-440   
so Download the driver for your version.   
Download [Link](https://www.nvidia.co.kr/Download/driverResults.aspx/156786/kr)   
file name is "NVIDIA-Linux-x86_64-440.59.run"   

```

3. Install   

```bash
Press ctrl+alt+f2 on the login screen   
Enter the ID/PWD 

# cd Download
# chmod +x ./NVIDIA-Linux-x86_64-440.59.run   
# sudo sh ./NVIDIA-Linux-x86_64-440.59.run

Install!!!!!!

```

4. Confirm installation
```bash
# nvidia-smi

```


CUDA 10.2 Install
=========

```bash
# wget http://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda_10.2.89_440.33.01_linux.run 
# sudo sh cuda_10.2.89_440.33.01_linux.run

Export path
# export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
# nvcc -V
# sudo reboot

Open Bashrc file and 'sudo subl ~/.bashrc' and paste and update the bashrc

# export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
# export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
# source ~/.bashrc

Check Install status
# nvcc -V

```


## CUDNN Install
=========

check cudnn version and download
https://developer.nvidia.com/rdp/cudnn-archive

```bash
# cd download path
# sudo tar -xzvf cudnn-9.0-linux-x64-v7.0.tgz 
# cd cuda
# sudo cp include/cudnn.h /usr/local/cuda/include
# sudo cp lib64/libcudnn* /usr/local/cuda/lib64
# sudo chmod a+r /usr/local/cuda/lib64/libcudnn*

Check Install status
# cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2
```


