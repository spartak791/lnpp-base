FROM php:8.4.16-fpm

RUN apt-get update && apt-get install -y \
        libicu-dev \
        libpq-dev \
    && docker-php-ext-install -j$(nproc) opcache \
    && docker-php-ext-install -j$(nproc) intl \
    && docker-php-ext-install -j$(nproc) pgsql \
    && docker-php-ext-install -j$(nproc) pdo_pgsql
