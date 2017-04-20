FROM centos:7
MAINTAINER dev@cokapp.com

RUN mkdir -p /root/frp
WORKDIR /root/frp

#add exec
COPY ./bin/frpc ./frpc
RUN chmod +x ./frpc

#add conf
RUN mkdir /root/frp/conf
COPY ./frpc.ini ./conf/frpc.ini
VOLUME ["/root/frp/conf"]


ENTRYPOINT /root/frp/frpc
CMD ["/root/frp/frpc", "-c ./frpc.ini"]