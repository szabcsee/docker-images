# Application image
#
# This image mainly adds the latest application source to the base image
#
FROM php:7.4-apache

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli

COPY . /var/www/html

RUN chown -R www-data:www-data /var/www/html