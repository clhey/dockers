FROM centos:7
MAINTAINER dev@cokapp.com

RUN mkdir -p /home//frp

COPY frps /opt/frp/frps
RUN chmod +x /opt/frp/frps
COPY frps.ini /opt/frp/frps.ini

EXPOSE 4443 4444 80

ENTRYPOINT /opt/frp/frps -c /opt/frp/frps.ini
