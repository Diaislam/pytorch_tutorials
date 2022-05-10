# 2. Preparing your deep learning environment
 
###  <b> step 1 : os preparation </b>
 
- download and install ubuntu 18.04 [official link](https://releases.ubuntu.com/18.04/), if you are not sure how to install ubuntu alongside with your current os, follow this [link](https://phoenixnap.com/kb/how-to-install-ubuntu-18-04)
 
- install the necessary libraries

       $ sudo apt-get update
       $ sudo apt-get upgrade -y
       $ sudo apt-get install -y build-essential cmake unzip pkg-config
       $ sudo apt-get install -y libxmu-dev libxi-dev libglu1-mesa libglu1-mesa-dev
       $ sudo apt-get install -y libjpeg-dev libpng-dev libtiff-dev
       $ sudo apt-get install -y libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
       $ sudo apt-get install -y libxvidcore-dev libx264-dev
       $ sudo apt-get install -y libgtk-3-dev
       $ sudo apt-get install -y libopenblas-dev libatlas-base-dev liblapack-dev gfortran
       $ sudo apt-get install -y libhdf5-serial-dev graphviz
       $ sudo apt-get install -y python3-dev python3-tk python-imaging-tk
       $ sudo apt-get install -y linux-image-generic linux-image-extra-virtual
       $ sudo apt-get install -y linux-source linux-headers-generic
 
###  <b> step 2 : nvidia driver & cuda 11.4 (gpu) </b>
 
- install nvidia driver
 
       $ sudo add-apt-repository ppa:graphics-drivers/ppa
       $ sudo apt-get update
 
       # auto install version
       $ sudo ubuntu-drivers autoinstall 
 
       # or specify the version ie nvidia-driver-510
       $ sudo apt install nvidia-driver-[version-number]
 
       - restart your computer
       # verify installation with this command
       $ nvidia-smi
 
- if this method doesn't work with you, remove NVIDIA from your system and reinstall .
 
       # delete nvidia driver
       $ sudo apt-get purge nvidia*
 
       - restart your pc
       - reinstall nvidia driver
 
- download and install cuda 11.4
 
       $ wget https://developer.download.nvidia.com/compute/cuda/11.4.2/local_installers/cuda_11.4.2_470.57.02_linux.run
 
       $ sudo sh cuda_11.4.2_470.57.02_linux.run
 
       # after the installation if cuda isn't in your environment then add it to the files .bashrc
 
       $ sudo nano ~/.bashrc
       $ export PATH=/usr/local/cuda-11.4/bin${PATH:+:${PATH}}
       $ export LD_LIBRARY_PATH=/usr/local/cuda-11.4/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
       $ export CUDA_HOME=/usr/local/cuda
 
- download and install cudnn 8.2.4
 
       $ wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.2.2/11.4_07062021/cudnn-11.4-linux-x64-v8.2.2.26.tgz
       $ tar -zvxf cudnn-11.4-linux-x64-v8.2.2.26.tgz
       # add cudnn to your env change xxx with your path
       $ nano ~/.bashrc
       $ export LD_LIBRARY_PATH=xxx/cuda/lib64:$LD_LIBRARY_PATH
       $ source ~/.bashrc
       $ cd xxx/cuda/include
       $ sudo cp *.h /usr/local/cuda/include/
       # replace xxx with your own path
       $ sudo chmod a+r /usr/local/cuda/include/cudnn.h
 
       # Test that everything is setup
       $ nvidia-smi
       $ nvcc -V

### <b> congratulations you are all setup!