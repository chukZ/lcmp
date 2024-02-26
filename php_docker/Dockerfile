FROM php:8.3-fpm-alpine

# Downloading install-php-extensions script and making it executable
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/install-php-extensions
RUN chmod +x /usr/local/bin/install-php-extensions

# Installing PHP extensions using install-php-extensions script
RUN install-php-extensions \
    mysqli \
    pdo \
    pdo_mysql \
    gd \
    zip \
    intl \
    xml \
    curl \
    dom \
    fileinfo \
    iconv \
    json \
    libxml \
    mbstring \
    openssl \
    pcre \
    phar \
    simplexml \
    zlib

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Cleaning APK cache
RUN rm -rf /var/cache/apk/*
