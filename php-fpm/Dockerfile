ARG PHP_FPM_VERSION

FROM php:${PHP_FPM_VERSION}-fpm

#RUN mkdir /wwwroot
#RUN chown -R www-data:www-data /wwwroot
#RUN chmod -R 777 /wwwroot

ARG PHP_FPM_CONTAINER_PORT=${PHP_FPM_CONTAINER_PORT}
EXPOSE ${PHP_FPM_CONTAINER_PORT}

RUN docker-php-ext-install pdo_mysql

#CMD ["php-fpm", "-v"]
