FROM php:fpm-alpine

RUN apk update

RUN apk add libpq-dev

RUN docker-php-ext-install pdo pdo_pgsql opcache

COPY --from=composer/composer:latest-bin /composer /usr/bin/composer
COPY /site /var/www/site

WORKDIR /var/www/site

ENV COMPOSER_ALLOW_SUPERUSER=1

RUN composer install