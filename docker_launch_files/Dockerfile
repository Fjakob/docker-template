FROM ubuntu:20.04

### Make installation non interactive so that docker doesnt crash during build
ENV DEBIAN_FRONTEND noninteractive

### OS setup
RUN apt-get update -y &&\
    apt-get install -y --no-install-recommends &&\
    apt-get install python3.10 -y &&\
    apt install python3-pip -y &&\
    apt install -y python3-tk

### Install basic python packages
RUN pip install --upgrade pip &&\
    pip install numpy==1.23.1 &&\
    pip install matplotlib==3.5.2 &&\
    pip install notebook

### needed for plotting
RUN apt install python3-gi-cairo

### Entry point
WORKDIR /docker_volume
CMD ["/bin/bash"]

### Important: for every reboot: run xhost +local:docker
