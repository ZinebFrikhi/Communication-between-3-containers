#server php
FROM php:7.3-fpm-alpine
#comme htdocs, work directory
WORKDIR /var/www

#Update functionalities of the server
RUN apk update && apk add \
    build-base \
    vim
#install mysql driver or pdo
RUN docker-php-ext-install  mysqli pdo  pdo_mysql \
    && docker-php-ext-enable pdo_mysql
#in server php m its necessary to add group and user
RUN addgroup -g 1000 -S www && \
    adduser -u 1000 -S www -G www


USER www

#Copy my files dans dak htdocs
COPY --chown=www:www . /var/www

#port
EXPOSE 9000
