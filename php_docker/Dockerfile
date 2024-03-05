FROM php:8.2-fpm-alpine

# Downloading install-php-extensions script and making it executable
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

# Making install-php-extensions script executable
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

# Setting PHP directives
RUN echo 'memory_limit = 512M' > /usr/local/etc/php/conf.d/memory-limit.ini
RUN echo 'max_execution_time = 300' > /usr/local/etc/php/conf.d/max-execution-time.ini
RUN echo 'max_input_vars = 10000' > /usr/local/etc/php/conf.d/max-input-vars.ini
RUN echo 'max_input_time = 300' > /usr/local/etc/php/conf.d/max-input-time.ini
RUN echo 'opcache.revalidate_freq=0' > /usr/local/etc/php/conf.d/opcache-revalidate-freq.ini
RUN echo 'opcache.validate_timestamps=0' > /usr/local/etc/php/conf.d/opcache-validate-timestamps.ini
RUN echo 'opcache.max_accelerated_files=7963' > /usr/local/etc/php/conf.d/opcache-max-accelerated-files.ini
RUN echo 'opcache.memory_consumption=256' > /usr/local/etc/php/conf.d/opcache-memory-consumption.ini
RUN echo 'opcache.interned_strings_buffer=16' > /usr/local/etc/php/conf.d/opcache-interned-strings-buffer.ini
RUN echo 'opcache.fast_shutdown=1' > /usr/local/etc/php/conf.d/opcache-fast-shutdown.ini

# Cleaning up
RUN rm -rf /var/cache/apk/*
