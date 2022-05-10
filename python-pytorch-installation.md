### <b> installing Python </b>
method 1: create a virtual environment for python :
<br>
- it is recommanded to use a python version >=3.6

       $ sudo apt-get update && sudo apt-get upgrade
       $ sudo apt install python3.x
       # you can specify the python version if it is installed by adding the flag --python=python3.x
       $ sudo apt install python3-venv
       $ sudo apt install -y python3-pip
       $ python3 -m venv 'environement_name' # you can use pytorch as a name
       $ source 'environement_name'/bin/activate
       # packages for a robust setup
       $ sudo apt install build-essential libssl-dev libffi-dev python3-dev
 
 
method 2: install miniconda to manage virtual envs :
 
- download & install miniconda for ubuntu from this [link](https://docs.conda.io/en/latest/miniconda.html#:~:text=Miniconda%20is%20a%20free%20minimal,zlib%20and%20a%20few%20others.)
 
- create your python environment with
 
       $ conda create -n "env_name" python=3.x
 
- activate your environment with
 
       $ conda activate "env_name"
 
- proceed and install your python libraries with pip
 
<br>

### <b> installing PyTorch </b>

- activate your environment 
    
        $ conda activate "env_name"
        or 
        $ source env_name/bin/activate

- install pytorch
 
        $ pip install torch torchvision torchaudio

        or a specific version

        $ pip install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1

        # test pytorch installation
        $ python
        $ import torch

        # test if pytorch is using gpu
        $ torch.cuda.is_available() # should return True

        # if no errors are shown they your pytorch is installed

        # if you are going to install pytorch on cpu s
        $ pip install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 cpuonly 