FROM centos

RUN yum upgrade -y && \
    yum update -y && \
    yum install -y git java-1.8.0-openjdk-devel maven gcc gcc-c++ make cmake tar curl-devel expat-devel wget

RUN useradd -m gates

USER gates

COPY docker_bashrc /home/gates/.bashrc
COPY docker_inputrc /home/gates/.inputrc
