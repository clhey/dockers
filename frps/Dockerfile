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

EXPOSE 700 800 80 443

ENTRYPOINT /root/frp/frps
CMD ["/root/frp/frps", "-c ./conf/frps.ini"]
