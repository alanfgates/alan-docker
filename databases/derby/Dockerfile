FROM centos

RUN yum upgrade -y && \
    yum update -y && \
    yum install -y java-1.8.0-openjdk-devel wget tar && \
    wget http://archive.apache.org/dist/db/derby/db-derby-10.10.1.1/db-derby-10.10.1.1-bin.tar.gz -P /root && \
    (cd /root; tar zxf db-derby-10.10.1.1-bin.tar.gz)
    
