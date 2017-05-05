FROM nginx:1.12
MAINTAINER clhey@cokapp.com

# copy app
COPY nginx.conf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/*
COPY ./conf.d /etc/nginx/conf.d

VOLUME ["/etc/nginx/conf.d"]

EXPOSE 80 443