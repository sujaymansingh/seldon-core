FROM nvidia/cuda:10.0-cudnn7-runtime-ubuntu18.04
# FROM nvidia/cuda:9.0-cudnn7-runtime-ubuntu16.04

LABEL io.openshift.s2i.scripts-url="image:///s2i/bin"

RUN apt-get update -y

# RUN apt-get install -y python
# RUN apt-get install -y python3

RUN apt-get install -y python-pip python-dev build-essential
RUN apt-get install -y python3-pip python3-dev

RUN mkdir microservice
WORKDIR /microservice

COPY ./s2i/bin/ /s2i/bin

# keep install of seldon-core after the COPY to force re-build of layer
RUN pip3 install tensorflow-gpu==1.13.1
RUN pip3 install seldon-core

EXPOSE 5000
