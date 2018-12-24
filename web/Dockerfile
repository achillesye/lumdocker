
ARG NGINX_VERSION=${NGINX_VERSION}

#FROM achilles12/cenlaravel:v1.0
FROM cenlaravel

#ARG PHP_FPM_CONTAINER_NAME=${PHP_FPM_CONTAINER_NAME}
#ARG PHP_FPM_CONTAINER_PORT=${PHP_FPM_CONTAINER_PORT}
ARG SERVER_WWW_ROOT=${SERVER_WWW_ROOT}

#RUN echo "upstream php-upstream { server ${PHP_FPM_CONTAINER_NAME}:${PHP_FPM_CONTAINER_PORT}; }" > /etc/nginx/conf.d/upstream.conf

#yum install php72w-mysqlnd -y

COPY ./supervisord/laravel.ini /etc/supervisord.d/

RUN echo "* * * * * root php ${SERVER_WWW_ROOT}xtx1v1-server/artisan schedule:run >> /var/log/crontab.log 2>&1" >> /etc/crontab

EXPOSE 80 443


ENTRYPOINT ["bash", "/start.sh"]
