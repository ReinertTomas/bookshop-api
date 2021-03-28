FROM php:8-fpm-alpine

# https://github.com/mlocati/docker-php-extension-installer
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && sync

RUN install-php-extensions @composer \
    gd \
    pdo_mysql

COPY ./ /var/www/html/

WORKDIR /var/www/html/

CMD ["php-fpm"]

EXPOSE 9000