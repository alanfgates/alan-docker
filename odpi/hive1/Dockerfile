FROM centos

# Basic hygene
RUN yum upgrade -y && \
    yum update -y && \
    yum install -y java-1.8.0-openjdk-devel wget sudo unzip git maven

# Get Hadoop
RUN mkdir /grid && \
    cd /grid &&  \
    wget http://mirrors.sonic.net/apache/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz &&  \
    tar zxf hadoop-2.7.3.tar.gz

# Get Hive
RUN cd /grid &&  \
    wget http://mirror.nexcess.net/apache/hive/hive-1.2.1/apache-hive-1.2.1-bin.tar.gz &&  \
    tar zxf apache-hive-1.2.1-bin.tar.gz

# Get bigtop
RUN mkdir /git && \
    cd /git && \
    git clone https://github.com/alanfgates/bigtop.git && \
    cd bigtop && \
    git checkout --track origin/odpi-master

# Set up environment variables
RUN echo "export HIVE_HOME=/grid/apache-hive-1.2.1-bin" >> /root/.bash_profile
RUN echo "export HADOOP_HOME=/grid/hadoop-2.7.3" >> /root/.bash_profile
RUN echo "export PATH=$PATH:$HADOOP_HOME/bin:$HIVE_HOME/bin" >> /root/.bash_profile
RUN echo "export JAVA_HOME=/usr" >> /root/.bash_profile

RUN mkdir /root/hdfs-scratch

# Don't forget to put $HIVE_HOME/bin in the path

# ./gradlew :bigtop-tests:spec-tests:runtime:test -Pspec.tests -Dtest.single=TestBeeline -Dodpi.test.hive.jdbc.url=jdbc:hive2://localhost:10000 -Dodpi.test.hive.jdbc.user=root -Dodpi.test.hive.jdbc.password="" -Dodpi.test.hive.conf.dir=$HIVE_HOME/conf -Dodpi.test.hadoop.conf.dir=$HADOOP_HOME/conf -Dodpi.test.hive.location=/root/hdfs-scratch -Dodpi.test.hive.metastore.url=thrift://localhost:9083

# hive --service hiveserver2 --hiveconf datanucleus.schema.autoCreateAll=true --hiveconf hive.metastore.schema.verification=false

# hive --service metastore --hiveconf hive.metastore.uris=thrift://localhost:9083 --hiveconf datanucleus.schema.autoCreateAll=true --hiveconf hive.metastore.schema.verification=false
