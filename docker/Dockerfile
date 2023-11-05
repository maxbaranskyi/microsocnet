FROM php:8.2-apache

USER root

RUN addgroup --gid 1001 appuser; \
  adduser --uid 1001 --gid 1001 --disabled-password appuser; \
  adduser www-data appuser;

WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
        libpng-dev \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        zip \
        curl \
        unzip \
    && docker-php-ext-configure gd \
    && docker-php-ext-install \
        -j$(nproc) gd \
        pdo_mysql \
        mysqli \
        zip \
    && docker-php-source delete

RUN pecl install xdebug && docker-php-ext-enable xdebug

COPY docker-php-ext-xdebug.ini /usr/local/etc/php/conf.d/

COPY host.conf /etc/apache2/sites-available/000-default.conf

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN chown -R www-data:www-data /var/www/html \
    && a2enmod rewrite
