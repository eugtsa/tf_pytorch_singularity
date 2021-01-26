Bootstrap: docker
From: neurodebian:latest

%help

    Container with Anaconda 3 (Conda 2020.11) and pytorch, tf and notebooks environment from neurodebian.
    This installation is based on Python 3.8

%files
  ./requirements.txt /requirements.txt

%post
  
  apt-get update
  
  DEBIAN_FRONTEND=noninteractive apt-get -yq install \
    build-essential \
    wget \
    unzip \
    git \
    libxml2-dev \
    libssl-dev \
    libcurl4-openssl-dev \
    libgit2-dev \
    libssh2-1-dev \
    python3-setuptools \

  apt-get update
  
  wget -c https://repo.anaconda.com/archive/Anaconda3-2020.11-Linux-x86_64.sh
    /bin/bash Anaconda3-2020.11-Linux-x86_64.sh -bfp /usr/local

  #Conda configuration of channels from .condarc file

  conda config --add channels defaults
  conda config --add channels conda-forge
  conda config --add channels pytorch
  conda update conda

  #Install environment
   conda install --file requirements.txt

