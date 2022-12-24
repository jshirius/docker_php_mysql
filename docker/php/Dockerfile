FROM php:7.3-apache
RUN apt-get update  && docker-php-ext-install pdo_mysql mysqli mbstring
RUN apt-get install -y unzip

WORKDIR /var/www/html

EXPOSE 80