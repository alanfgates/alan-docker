FROM centos

# Basic hygene
RUN yum upgrade -y && \
    yum update -y && \
    yum install -y java-1.8.0-openjdk-devel wget sudo unzip git maven

RUN useradd -m gates

COPY docker_bashrc ~gates/.bashrc
COPY docker_inputrc ~gates/.inputrc


