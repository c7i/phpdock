FROM webdevops/nginx-dev:alpine

ARG NGINX_PHP_UPSTREAM_CONTAINER=php-fpm
ARG NGINX_PHP_UPSTREAM_PORT=9000

RUN rm /etc/nginx/conf.d/* \
    && echo "upstream php-upstream { server ${NGINX_PHP_UPSTREAM_CONTAINER}:${NGINX_PHP_UPSTREAM_PORT}; }" > /etc/nginx/conf.d/00-upstream.conf \
    && echo "include /etc/nginx/sites-available/*.conf;" > /etc/nginx/conf.d/10-vhosts.conf

EXPOSE 80 443
