FROM php:7.4
COPY php.ini /usr/local/etc/php

RUN apt-get update && \
	   apt-get install -y libzip-dev zlib1g-dev  && \
    docker-php-ext-install zip

#Composer install
COPY --from=composer /usr/bin/composer /usr/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1

ENV COMPOSER_HOME /composer

ENV PATH $PATH:/composer/vendor/bin


WORKDIR /var/www

RUN composer global require "laravel/installer"
