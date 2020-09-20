#FROM ubuntu:xenial
FROM nginx:latest
RUN apt-get update && apt-get install -y nginx-extras

# Overwrite default nginx configuration
RUN rm -f /etc/nginx/conf.d/*

COPY ./nginx/conf/nginx.conf /etc/nginx/
COPY ./nginx/conf/conf.d/*.conf /etc/nginx/conf.d/
COPY ./nginx/conf/proxy.conf /etc/nginx/
COPY ./nginx/conf/auth.conf  /etc/nginx/

EXPOSE 80