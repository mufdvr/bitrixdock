FROM devilbox/php-fpm-5.3:latest

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
    php5-memcached \
    php5-memcache \
    php5-mysql \
    php5-intl \
    php5-xdebug \
    php5-interbase \
    php5-gd \
    php5-imagick \
    php5-mcrypt \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN usermod -u 1000 www-data

ADD ./php.ini /etc/php5/fpm/conf.d/90-php.ini
ADD ./php.ini /etc/php5/cli/conf.d/90-php.ini

RUN usermod -u 1000 www-data

WORKDIR "/var/www/bitrix"

EXPOSE 9000
