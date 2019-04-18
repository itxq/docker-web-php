FROM php:7.2-fpm

MAINTAINER itxq <af2e@foxmail.com>

#将默认的用户1000 加入到 www-data 这个组里
RUN usermod -u 1000 www-data

RUN docker-php-source extract \
    # 安装扩展
    && docker-php-ext-install pdo pdo_mysql mysqli sockets pcntl mbstring \
    && docker-php-source delete

# 安装 Composer
ENV COMPOSER_HOME /root/composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV PATH $COMPOSER_HOME/vendor/bin:$PATH
