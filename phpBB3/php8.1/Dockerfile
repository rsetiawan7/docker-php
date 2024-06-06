FROM php:8.1-apache

RUN \
  apt-get update

RUN \
  apt-get install -y \
    libedit-dev \
    libfreetype-dev \
    libgmp-dev \
    libjpeg-dev \
    libpng-dev \
    libzip-dev \
    libcurl4-gnutls-dev \
    zlib1g-dev \
    && rm -rf /var/lib/apt/lists/*

RUN \
  docker-php-ext-configure \
    gd --with-jpeg --with-freetype

RUN \
  docker-php-ext-install -j$(nproc) \
    bcmath \
    curl \
    gd \
    mysqli \
    opcache \
    zip

RUN \
  docker-php-ext-enable \
    bcmath \
    curl \
    gd \
    mysqli \
    opcache \
    zip

RUN a2enmod rewrite

EXPOSE 80
