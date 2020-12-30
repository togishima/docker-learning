FROM php:7.4-fpm-alpine

RUN apk update && apk upgrade \
    && apk --update add curl \
    && apk --no-cache add \
    postgresql-dev php-pgsql autoconf build-base

RUN docker-php-ext-install pdo_mysql mysqli

# xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer