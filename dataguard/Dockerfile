from bigtruedata/sbt

RUN useradd -m gates

USER gates

COPY docker_bashrc /home/gates/.bashrc
COPY docker_inputrc /home/gates/.inputrc

WORKDIR /home/gates

VOLUME /home/gates/git/snowplow
