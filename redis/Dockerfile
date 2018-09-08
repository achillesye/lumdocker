
ARG REDIS_VERSION

FROM redis:${REDIS_VERSION}

RUN mkdir -p /etc/redis/

#RUN echo 511 > /proc/sys/net/core/somaxconn

COPY ./updatehugepage.sh /updatehugepage.sh

EXPOSE 6379

#CMD ["/bin/bash", "/updatehugepage.sh"]
#RUN /bin/bash -c 'echo never | tee /sys/kernel/mm/transparent_hugepage/enabled'

CMD ["redis-server", "/etc/redis/redis.conf"]
