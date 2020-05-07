FROM php:7.3-fpm-alpine

ARG TZ

RUN adduser -D -H -s /bin/sh -u 101 nginx

# RUN apk add shadow

RUN mkdir -p /var/run/php-fpm && chown nginx:nginx /var/run/php-fpm

COPY php.ini /usr/local/etc/php
COPY www.conf /usr/local/etc/php-fpm.d/zz-docker.conf

# RUN apk --update add --no-cache tzdata && \
#     cp /usr/share/zoneinfo/${TZ} /etc/localtime && \
#     apk del tzdata