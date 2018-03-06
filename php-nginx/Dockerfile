ARG PHP_VERSION=7.2
FROM webdevops/php-nginx:${PHP_VERSION}

# 添加vhost支持
RUN echo "include /opt/nginx_sites/*.conf;" > /opt/docker/etc/nginx/conf.d/00-vhost.conf

# 添加phpinfo() web root
RUN echo "<?php\nphpinfo();" > /app/index.php

# 配置composer加速镜像
ARG PHP_COMPOSER_REPO_PACKAGIST=https://packagist.phpcomposer.com
ENV PHP_COMPOSER_REPO_PACKAGIST ${PHP_COMPOSER_REPO_PACKAGIST}
RUN composer config -g repo.packagist composer ${PHP_COMPOSER_REPO_PACKAGIST}
