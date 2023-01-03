FROM php:7.3-apache

# 設定ファイルの設定
ADD 000-default.conf /etc/apache2/sites-enabled/

# PHPと一緒にライブラリーもインストール
RUN apt-get update  && docker-php-ext-install pdo_mysql mysqli mbstring

# unzipなどの必要ライブラリも一緒にインストール
RUN apt-get install -y unzip  \
git \
zip \
unzip \
vim \
libpng-dev \
libpq-dev

# ログイン直後のディレクトリを指定する
WORKDIR /var/www/html

# Composerをインストールする(Docker 17.05以上)
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Laravelで必要になるmodRewriteを有効化する(.htaccessの利用)
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite

EXPOSE 80