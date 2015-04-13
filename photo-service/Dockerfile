FROM        phusion/baseimage:latest
MAINTAINER  Brian Voss <brian@brianvoss.com>

RUN apt-get update; apt-get install -y php5-cli git;

# AMQP
RUN apt-get install -y php5-dev php-pear librabbitmq1 librabbitmq-dev;
RUN pecl install amqp;
RUN echo 'extension=amqp.so' > /etc/php5/mods-available/amqp.ini;
RUN ln -s /etc/php5/mods-available/amqp.ini /etc/php5/cli/conf.d/

RUN mkdir /var/www
RUN chown www-data:www-data /var/www

RUN cd /var/www/ && curl -sS https://getcomposer.org/installer | php
RUN cd /var/www/ && php composer.phar install

ADD etc/my_init.d/photo-service /etc/my_init.d/photo-service
RUN chmod +x /etc/my_init.d/*