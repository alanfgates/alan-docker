FROM centos

# Install required packages
RUN yum upgrade -y && \
    yum update -y && \
    yum install -y postgresql-server postgresql-jdbc java-1.8.0-openjdk-devel wget sudo


# Initialize and start postgres
RUN sudo -u postgres initdb -D /var/lib/pgsql/data/ && \
    mkdir /var/log/postgres && \
    chown postgres /var/log/postgres && \
    sudo -u postgres pg_ctl start -l /var/log/postgres/logfile -D /var/lib/pgsql/data && \
    sleep 30 && \
    sudo -u postgres createuser hive && \
    sudo -u postgres createdb -O hive hive

