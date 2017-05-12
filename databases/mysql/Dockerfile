FROM centos

# Install required packages
RUN yum upgrade -y && \
    yum update -y 

RUN yum install -y mariadb-server mariadb mysql-connector-java* java-1.8.0-openjdk-devel sudo hostname

RUN sudo -u mysql mysql_install_db

