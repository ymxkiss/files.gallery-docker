FROM php:7.4.9-fpm-alpine

COPY php.ini $PHP_INI_DIR/conf.d/

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd xdebug
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

RUN install-php-extensions GD mbstring fileinfo exif

RUN apk update && apk add ffmpeg
