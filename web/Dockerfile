FROM        phusion/baseimage:latest
MAINTAINER  Brian Voss <brian@brianvoss.com>

RUN apt-get update; apt-get install -y unzip wget git tar nginx npm bower
ADD etc /etc
ADD frontend /frontend
RUN sudo service nginx restart;
