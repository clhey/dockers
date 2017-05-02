FROM debian:jessie
MAINTAINER dev@cokapp.com

ENV NGROK_GIT https://github.com/inconshreveable/ngrok.git
ENV NGROK_BASE_DOMAIN ngrok.cko.pub
ENV NGROK_DIR /ngrok
ENV NGROK_TMP /tmp/ngrok

ENV NGROK_CA_KEY assets/client/tls/ngrokroot.key
ENV NGROK_CA_CRT assets/client/tls/ngrokroot.crt
ENV NGROK_SERVER_KEY assets/server/tls/snakeoil.key
ENV NGROK_SERVER_CSR assets/server/tls/snakeoil.csr
ENV NGROK_SERVER_CRT assets/server/tls/snakeoil.crt

WORKDIR $NGROK_DIR

#install pkg
RUN apt-get update \
    && apt-get install -y build-essential \
                          curl \
                          git \
                          golang \
                          mercurial
#clone ngrok src
RUN git clone ${NGROK_GIT} ${NGROK_TMP} \

RUN cd ${NGROK_TMP}

#copy ca
COPY bin/ngrok.cko.pub.pem assets/client/tls/ngrokroot.crt
COPY bin/ngrok.cko.pub.pem assets/server/tls/snakeoil.crt
COPY bin/ngrok.cko.pub.key assets/server/tls/snakeoil.key

#make
RUN make release-server

RUN cd ${NGROK_DIR}

EXPOSE 80 443 4443

ENTRYPOINT ["./ngrokd"]
