FROM centos

# Basic hygene
RUN yum upgrade -y && \
    yum update -y && \
    yum install -y java-1.8.0-openjdk-devel wget sudo unzip git maven which

RUN useradd -m gates
