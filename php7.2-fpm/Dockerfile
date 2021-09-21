FROM php:7.2-fpm-buster

RUN apt-get update && apt-get install -y \
        git \
        zip \
        libzip-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev libwebp-dev \
        libicu-dev \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-install pdo_mysql gd exif gettext opcache pcntl zip \
    && curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer
