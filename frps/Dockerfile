FROM centos:7
MAINTAINER dev@cokapp.com

RUN mkdir -p /root/frp
WORKDIR /root/frp

COPY ./bin/frps ./frps
RUN chmod +x ./frps
COPY ./frps.ini ./frps.ini

EXPOSE 700 800 80 443

ENTRYPOINT /root/frp/frps -c ./frps.ini
