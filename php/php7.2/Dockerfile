FROM php:7.2-fpm

RUN docker-php-source extract \
    # 安装PDO扩展
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-source delete

