ARG NGINX_VERSION=${NGINX_VERSION}

FROM nginx:${NGINX_VERSION}

#RUN chmod -R 777 /var/log/nginx/
#RUN mkdir /wwwroot
#RUN chown -R www-data:www-data /wwwroot
#RUN ln -sf /dev/stdout /var/log/nginx/access.log \
#	&& ln -sf /dev/stderr /var/log/nginx/error.log

ARG PHP_FPM_CONTAINER_NAME=${PHP_FPM_CONTAINER_NAME}
ARG PHP_FPM_CONTAINER_PORT=${PHP_FPM_CONTAINER_PORT}

RUN echo "upstream php-upstream { server ${PHP_FPM_CONTAINER_NAME}:${PHP_FPM_CONTAINER_PORT}; }" > /etc/nginx/conf.d/upstream.conf


EXPOSE 80 443
