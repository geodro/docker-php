FROM php:8.0-fpm

# fix work iconv library with alphine
RUN apt-get update && apt-get install -y \
        git \
        libzip-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev libwebp-dev \
        libicu-dev \
    && docker-php-ext-configure gd --with-freetype=/usr/include/ --with-webp=/usr/include/  --with-jpeg=/usr/include/ \
    && docker-php-ext-install pdo_mysql gd exif gettext opcache pcntl zip intl \
    && curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer