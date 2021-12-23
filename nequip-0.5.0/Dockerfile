#Create ubuntu as base image
FROM pytorch/pytorch:1.9.0-cuda10.2-cudnn7-runtime

ENV BASH_ENV ~/.bashrc
SHELL ["/bin/bash", "-c"]
WORKDIR /home/mphuthi

#Install packages
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt install -y wget
RUN apt install -y git
RUN apt install -y vim
RUN sh -c "$(wget https://raw.github.com/ohmybash/oh-my-bash/master/tools/install.sh -O -)"
RUN git clone https://github.com/materialstools/dockerfiles.git
RUN conda create -n nequip
RUN conda init bash
# RUN eval "$(conda shell.bash hook)"
RUN echo "conda activate nequip" >> ~/.bashrc
RUN conda install --name nequip python==3.9
RUN conda activate nequip
RUN pip3 install torch==1.9.0+cu102 -f https://download.pytorch.org/whl/cu102/torch_stable.html
RUN conda env update -f dockerfiles/nequip-0.5.0/environment.yaml
RUN conda install pyg -c pyg -c conda-forge
RUN git clone https://github.com/mir-group/nequip.git
RUN cd nequip
RUN pip install .
# RUN pip install nequip
    # - torch-ema==0.2
    # - torch-geometric==1.7.2
    # - torch-runstats==0.1.0
    # - torch-scatter==2.0.8
    # - torch-sparse==0.6.12


#Install packages
# RUN yum -y install wget
# RUN yum -y install git
# RUN touch .bashrc
# RUN sh -c "$(wget https://raw.github.com/ohmybash/oh-my-bash/master/tools/install.sh -O -)"
# RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
# RUN bash Miniconda3-latest-Linux-x86_64.sh -b -p install/miniconda3
# ENV PATH="/home/mphuthi/install/miniconda3/bin:${PATH}"
# RUN git clone https://github.com/materialstools/dockerfiles.git
# RUN conda create -n nequip
# RUN conda init bash
# RUN source activate nequip
# RUN conda install python==3.9
# RUN pip3 install torch==1.9.0+cu102 -f https://download.pytorch.org/whl/cu102/torch_stable.html
# RUN conda env update -f dockerfiles/nequip-0.5.0/environment.yaml



