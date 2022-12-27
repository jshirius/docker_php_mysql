FROM php:7.3-apache

# 設定ファイルの設定
ADD 000-default.conf /etc/apache2/sites-enabled/

RUN apt-get update  && docker-php-ext-install pdo_mysql mysqli mbstring
RUN apt-get install -y unzip  \
git \
zip \
unzip \
vim \
libpng-dev \
libpq-dev

WORKDIR /var/www/html

# Laravelで必要になるmodRewriteを有効化する
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite

EXPOSE 80