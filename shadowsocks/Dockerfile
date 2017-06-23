FROM ubuntu:16.04
MAINTAINER dev@cokapp.com

RUN apt-get update && \
    apt-get install -y python-pip libsodium18
RUN pip install shadowsocks==3.0.6

#add conf
RUN mkdir /root/shadowsocks/conf
COPY ./shadowsocks.json /root/shadowsocks/conf/shadowsocks.json
VOLUME ["/root/shadowsocks/conf"]

ENTRYPOINT ["/usr/local/bin/ssserver"]
CMD ["-c", "/root/shadowsocks/conf/shadowsocks.json"]