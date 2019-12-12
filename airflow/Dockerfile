FROM centos

# Basic hygene
RUN yum upgrade -y && \
    yum update -y

RUN yum install -y gcc python-devel which screen

RUN yum install -y epel-release
RUN yum install -y python-pip
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools

RUN useradd -m gates

RUN mkdir /home/gates/airflow
ENV SLUGIFY_USES_TEXT_UNIDECODE=yes
ENV AIRFLOW_HOME=/home/gates/airflow
RUN pip install apache-airflow

RUN chown gates /home/gates/airflow
USER gates


COPY docker_bashrc /home/gates/.bashrc
COPY docker_inputrc /home/gates/.inputrc

WORKDIR /home/gates
EXPOSE 8080

RUN airflow initdb
#CMD [ "/bin/bash", "-c", \
#     "(airflow webserver -p 8080 & 2>&1 > /home/gates/webserverlogs; airflow scheduler & 2>&1 > /home/gates/schedulerlogs)" ]

