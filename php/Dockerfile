FROM php:7.2-fpm

MAINTAINER RUSLAN ROZHKOV <ruslan399@gmail.com>

RUN apt-get update \
    && ln -sf /usr/share/zoneinfo/Europe/Moskow /etc/localtime \
    && apt-get install -y -q \
        git \
        jpegoptim \
        optipng \
        pngquant \
        gifsicle \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libxml2-dev \
    && docker-php-ext-install -j$(nproc) mbstring pdo_mysql zip xml

RUN usermod -u 1000 www-data

RUN git clone https://github.com/rus-lan/image-optimizer.git

CMD ["php-fpm"]
