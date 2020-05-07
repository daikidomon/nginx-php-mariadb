FROM nginx:1.17-alpine

ARG TZ

COPY php-fpm.conf /etc/nginx/conf.d/default.conf

RUN apk add --update --no-cache tzdata && \
    cp /usr/share/zoneinfo/${TZ} /etc/localtime && \
    echo ${TZ} > /etc/timezone && \
    apk del tzdata

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]