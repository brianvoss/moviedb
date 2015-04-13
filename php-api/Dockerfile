FROM        phusion/baseimage:latest
MAINTAINER  Brian Voss <brian@brianvoss.com>

RUN apt-get update; apt-get install -y php5-fpm git;

# AMQP
RUN apt-get install -y php5-dev php-pear librabbitmq1 librabbitmq-dev;
RUN pecl install amqp;
RUN echo 'extension=amqp.so' > /etc/php5/mods-available/amqp.ini;
RUN ln -s /etc/php5/mods-available/amqp.ini /etc/php5/cli/conf.d/
RUN ln -s /etc/php5/mods-available/amqp.ini /etc/php5/fpm/conf.d/

ADD etc/my_init.d/fpm-config /etc/my_init.d/fpm-config
RUN chmod +x /etc/my_init.d/*

RUN useradd -u 1000 php -g 33
RUN mkdir /var/www
RUN chown php:www-data /var/www