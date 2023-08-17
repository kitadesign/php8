FROM php:8.2-fpm

COPY php.ini /usr/local/etc/php/php.ini
COPY zz-docker.conf /usr/local/etc/php-fpm.d/zz-docker.conf

RUN set -eux; \
  apt-get update; \
  apt-get upgrade -y; \
  apt-get install -y --no-install-recommends \
  git \
  curl \
  zip \
  unzip

RUN set -eux; \
  apt-get install -y --no-install-recommends \
  libz-dev \
  libpq-dev \
  libjpeg-dev \
  libpng-dev \
  libfreetype6-dev \
  libssl-dev \
  libwebp-dev \
  libxpm-dev \
  libmcrypt-dev \
  libonig-dev \
  libmemcached-dev; \
  rm -rf /var/lib/apt/lists/*

RUN set -eux; \
  docker-php-ext-install pdo_mysql; \
  docker-php-ext-configure gd \
  --prefix=/usr \
  --with-jpeg \
  --with-webp \
  --with-xpm \
  --with-freetype; \
  docker-php-ext-install gd; \
  php -r 'var_dump(gd_info());'

WORKDIR /var/www
