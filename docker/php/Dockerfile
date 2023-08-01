FROM php:8.2-fpm

COPY custom.ini /usr/local/etc/php/php.ini

# Install dependencies
RUN apt update && \
    apt install --no-install-recommends -y \
    zlib1g-dev \
    libpng-dev \
    libzip-dev \
    unzip

RUN docker-php-ext-install  pdo pdo_mysql zip

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN pecl install xdebug && docker-php-ext-enable xdebug
