FROM debian:12
COPY data.txt /
RUN  apt update
RUN  apt install -y redis-server
RUN  useradd -m -s /bin/bash bob
RUN  mv /data.txt /data.txt.sav
WORKDIR /partage
EXPOSE 1234/udp
COPY startup.sh /
ARG  stage=curt
ENV  STAGE=${stage}
ENTRYPOINT ["/startup.sh"]
CMD ["hostname"]
