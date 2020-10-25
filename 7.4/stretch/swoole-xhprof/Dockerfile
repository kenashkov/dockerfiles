FROM kenashkov/php:7.4.8-swoole-4.5.2-root

RUN cd /root \
    && wget https://github.com/tideways/php-xhprof-extension/archive/v5.0.2.tar.gz \
    && tar -xzvf v5.0.2.tar.gz \
    && cd ./php-xhprof-extension-5.0.2 \
    && phpize \
    && ./configure \
    && make \
    && make install \
    && echo "extension=tideways_xhprof.so" > /usr/local/etc/php/conf.d/docker-php-ext-xhprof.ini

