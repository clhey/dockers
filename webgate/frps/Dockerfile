FROM centos:7
MAINTAINER dev@cokapp.com

RUN mkdir -p /root/frp
WORKDIR /root/frp

#add exec
COPY ./bin/frps ./frps
RUN chmod +x ./frps

#add conf
RUN mkdir /root/frp/conf
COPY ./frps.ini ./conf/frps.ini
VOLUME ["/root/frp/conf"]

EXPOSE 80 443 700 800

ENTRYPOINT ["/root/frp/frps"]
CMD ["-c", "./conf/frps.ini"]
