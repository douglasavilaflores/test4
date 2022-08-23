FROM php:7.4-fpm-alpine

# Set working directory
# WORKDIR /var/www

# Install dependencies
RUN apk update --no-cache \
&& apk add \
icu-dev \
oniguruma-dev \
tzdata

# Install extensions
RUN docker-php-ext-install intl

RUN docker-php-ext-install pcntl

RUN docker-php-ext-install pdo_mysql

RUN docker-php-ext-install mbstring
 
RUN rm -rf /var/cache/apk/*

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
 
CMD ["php-fpm"]