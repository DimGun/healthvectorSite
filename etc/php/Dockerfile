FROM php:7.1-fpm

RUN docker-php-ext-install mysqli pdo_mysql

WORKDIR /var/www/

COPY ./etc/php/log-stdout.conf /usr/local/etc/php-fpm.d/zz-log.conf
COPY ./etc/php/xdebug.ini /usr/local/etc/php/conf.d/

# Installing composer
COPY ./etc/php/composer.phar /usr/local/bin/composer
RUN chmod u+x /usr/local/bin/composer

# Registering PSR-4 autoloading classes
COPY ./composer.json /var/www/
RUN mkdir -p /var/www/vendor
RUN composer install

#RUN yes | pecl install xdebug
