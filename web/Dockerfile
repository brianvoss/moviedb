FROM        phusion/baseimage:latest
MAINTAINER  Brian Voss <brian@brianvoss.com>

RUN apt-get update; apt-get install -y unzip wget git tar nginx npm;
ADD etc /etc
RUN chmod +x /etc/my_init.d/*
ADD frontend /frontend
