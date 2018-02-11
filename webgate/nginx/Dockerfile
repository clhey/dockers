FROM nginx:1.12
LABEL maintainer="clhey@cokapp.com"

# copy app
COPY nginx.conf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/*
COPY ./conf.d /etc/nginx/conf.d
COPY ./_ssl /etc/nginx/_ssl

VOLUME ["/etc/nginx/conf.d"]

EXPOSE 80 443