FROM php:7.2-fpm

RUN docker-php-source extract \
    # 安装PDO mysql 扩展
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-source delete

# mysql sock
RUN echo "pdo_mysql.default_socket = /var/run/mysqld/mysqld.sock" >>  /usr/local/etc/php/conf.d/docker-php-ext-pdo_mysql.ini \
    && echo "mysql.default_socket = /var/run/mysqld/mysqld.sock" >> /usr/local/etc/php/conf.d/docker-php-ext-mysql.ini \
    && echo "mysqli.default_socket = /var/run/mysqld/mysqld.sock" >> /usr/local/etc/php/conf.d/docker-php-ext-mysqli.ini

# 安装 Composer
ENV COMPOSER_HOME /root/composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ENV PATH $COMPOSER_HOME/vendor/bin:$PATH
