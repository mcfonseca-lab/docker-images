FROM mcfonsecalab/python38_bio:latest
MAINTAINER Pedro Barbosa <pedro.barbosa@medicina.ulisboa.pt>

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install -y --no-install-recommends  \
       ca-certificates \
       cmake \
       curl \
       cython \
       g++ \
       gfortran \
       git \
       libblas-dev \
       libgsl-dev \
       liblapack-dev \
       python-setuptools \
       make \
       zlib1g-dev

#rmats, pairadise, and maser
RUN mamba install -c conda-forge -c bioconda rmats=4.1.1 bioconductor-maser
RUN git clone https://github.com/Xinglab/rmats-turbo.git
WORKDIR rmats-turbo
RUN git clone https://github.com/Xinglab/PAIRADISE.git && Rscript install_r_deps.R

#rmats2sashimi
RUN git clone https://github.com/Xinglab/rmats2sashimiplot.git
WORKDIR rmats2sashimiplot/
RUN ./2to3.sh && python ./setup.py install

WORKDIR /python_env
ADD run_maser.R .
