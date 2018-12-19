ARG PHP_FPM_VERSION

FROM php:${PHP_FPM_VERSION}-fpm


ARG PHP_FPM_CONTAINER_PORT=${PHP_FPM_CONTAINER_PORT}
ARG SERVER_WWW_ROOT=${SERVER_WWW_ROOT}

EXPOSE ${PHP_FPM_CONTAINER_PORT}

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install pdo_mysql 

RUN apt-get install -y cron 
#RUN crontab /etc/crontab

RUN echo "* * * * * root php ${SERVER_WWW_ROOT}xtx1v1-server/artisan schedule:run >> /var/log/crontab.log 2>&1" >> /etc/crontab

#ENTRYPOINT cron && tail -f /var/log/lastlog 

#CMD cron && tail -f /var/log/lastlog 
CMD cron -f & docker-php-entrypoint php-fpm
