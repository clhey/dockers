FROM debian:jessie

MAINTAINER Transmission Docker Maintainers "charlie@cokapp.com"

#RUN add-apt-repository -y ppa:transmissionbt/ppa && \
    #apt-get -q update && \
    #apt-get install -qy --force-yes transmission-daemon ca-certificates wget tar curl unrar-free procps && \
    #apt-get -y autoremove && \
    #apt-get -y clean && \
    #rm -rf /var/lib/apt/lists/* && \
    #rm -rf /tmp/*

RUN apt-get update && \
	apt-get install -y transmission-daemon


ADD ./settings.json /var/lib/transmission-daemon/info/settings.json
ADD ./start.sh /var/lib/transmission-daemon/start.sh
RUN chmod +x /var/lib/transmission-daemon/start.sh


EXPOSE 9091 51413

ENV USERNAME="admin" \
    PASSWORD="password"

VOLUME ["/downloads", "/incomplete", "/watch", "/config"]

WORKDIR /var/lib/transmission-daemon
#CMD ["./start.sh"]
CMD ["./start.sh"]