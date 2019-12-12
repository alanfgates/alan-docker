FROM ubuntu:18.04

RUN ln -fs /usr/share/zoneinfo/America/Los_Angeles /etc/localtime
RUN apt-get update
RUN apt-get install -y openjdk-8-jdk wget git python3
RUN apt-get install -y python3-pip

RUN python3 -m pip install flake8

RUN useradd -m gates

USER gates

COPY docker_bashrc /home/gates/.bashrc
COPY docker_inputrc /home/gates/.inputrc
