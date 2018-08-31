FROM hub.c.163.com/library/php:7.1-fpm
RUN apt-get update -y && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    libssl-dev \
    libxml2-dev \
    wget cmake

RUN docker-php-ext-install -j$(nproc) mcrypt pdo_mysql mysqli soap \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# # xdebug redis
# 网络问题不可用
# RUN pecl install redis-3.1.0 \
#     && pecl install xdebug-2.5.0 \
#     && docker-php-ext-enable redis xdebug

RUN wget http://pecl.php.net/get/redis-3.1.6.tgz \
  && mkdir -p /tmp/redis \
  && tar zxf redis-3.1.6.tgz -C /tmp/redis --strip-components=1 \
  && rm redis-3.1.6.tgz \
  && docker-php-ext-configure /tmp/redis --enable-redis \
  && docker-php-ext-install /tmp/redis \
  && rm -r /tmp/redis

RUN wget http://pecl.php.net/get/xdebug-2.5.5.tgz \
  && mkdir -p /tmp/xdebug \
  && tar zxf xdebug-2.5.5.tgz -C /tmp/xdebug --strip-components=1 \
  && rm xdebug-2.5.5.tgz \
  && docker-php-ext-configure /tmp/xdebug --enable-xdebug \
  && docker-php-ext-install /tmp/xdebug \
  && rm -r /tmp/xdebug

# yaf
RUN wget http://pecl.php.net/get/yaf-3.0.7.tgz \
  && mkdir -p /tmp/yaf \
  && tar zxf yaf-3.0.7.tgz -C /tmp/yaf --strip-components=1 \
  && rm yaf-3.0.7.tgz \
  && docker-php-ext-configure /tmp/yaf --enable-yaf \
  && docker-php-ext-install /tmp/yaf \
  && rm -r /tmp/yaf
