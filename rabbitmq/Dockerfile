FROM		phusion/baseimage
MAINTAINER	Brian Voss <brian@brianvoss.com>

RUN apt-get update;  apt-get install -y wget;

RUN wget https://www.rabbitmq.com/rabbitmq-signing-key-public.asc;
RUN apt-key add rabbitmq-signing-key-public.asc;

RUN apt-get install -y rabbitmq-server;

RUN rabbitmq-plugins enable rabbitmq_management;

ADD etc/my_init.d/rabbitmq-server /etc/my_init.d/rabbitmq-server
RUN chmod +x /etc/my_init.d/rabbitmq-server

# Expose ports.
EXPOSE 5672
EXPOSE 15672