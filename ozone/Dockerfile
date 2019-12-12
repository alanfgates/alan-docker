# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# ORC compile for CentOS 8
#

FROM centos:7

RUN yum check-update || true
RUN yum install -y \
  git \
  java-1.8.0-openjdk \
  java-1.8.0-openjdk-devel \
  protobuf-devel-2.5.0 \
  tar \
  wget \
  which

RUN (cd /usr/share; \
     wget http://apache-mirror.8birdsvideo.com/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.tar.gz; \
     tar zxf apache-maven-3.6.2-bin.tar.gz; \
     ln -s /usr/share/apache-maven-3.6.2/bin/mvn /usr/bin/mvn; \
    )

RUN useradd -m gates

USER gates

COPY docker_bashrc /home/gates/.bashrc
COPY docker_inputrc /home/gates/.inputrc

VOLUME /home/gates/git/hadoop-ozone

