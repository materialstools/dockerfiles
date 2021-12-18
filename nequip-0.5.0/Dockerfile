#Create ubuntu as base image
FROM centos

WORKDIR /home/mphuthi

#Install packages
RUN yum -y install wget
RUN yum -y install which
RUN yum -y install git
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN bash Miniconda3-latest-Linux-x86_64.sh -b -p install/miniconda3
ENV PATH="/home/mphuthi/install/miniconda3/bin:${PATH}"
RUN conda init bash

