FROM php:7.2-fpm

MAINTAINER IT小强xqitw.cn <mail@xqitw.cn>

# 设置时区
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#将默认的用户1000 加入到 www-data 这个组里
RUN usermod -u 1000 www-data

RUN docker-php-source extract \
    # 安装扩展
    && docker-php-ext-install pdo pdo_mysql mysqli sockets pcntl mbstring opcache \
    && docker-php-source delete

# 安装 Composer
ENV COMPOSER_HOME /root/composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV PATH $COMPOSER_HOME/vendor/bin:$PATH
