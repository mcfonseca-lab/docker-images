FROM mcfonsecalab/python37_bio

MAINTAINER Rui Luis  <rluis@medicina.ulisboa.pt>

RUN apt-get update
RUN apt-get install -y  build-essential

RUN conda update -n base conda

LABEL Vpychopper="v0.6.1"
RUN conda install -c bioconda pychopper=$Vpychopper

RUN apt-get autoclean -y

