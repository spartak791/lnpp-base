FROM php:8.4.16-fpm

RUN apt-get update && apt-get install -y \
        libicu-dev \
        libpq-dev \
        libzip-dev \
        git \
        7zip \
        unzip \
        zip

RUN docker-php-ext-install -j$(nproc) \
    opcache \
    intl \
    pgsql \
    pdo_pgsql \
    zip

COPY --from=composer/composer:2.9.2-bin /composer /usr/bin/composer
RUN mkdir /root/.composer \
  && curl --silent --fail --location --retry 3 --output /root/.composer/keys.dev.pub --url https://composer.github.io/snapshots.pub \
  && curl --silent --fail --location --retry 3 --output /root/.composer/keys.tags.pub --url https://composer.github.io/releases.pub
