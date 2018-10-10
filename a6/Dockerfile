FROM alpine
FROM phalconphp/php-fpm:5.6

RUN git clone https://github.com/nrk/predis.git /predis \
  && mv /predis/src /usr/share/php/Predis \
  && rm -rf /predis

ENV TIMEZONE Europe/Kiev
ENV PHP_MEMORY_LIMIT 1024M
ENV MAX_UPLOAD 128M
ENV PHP_MAX_FILE_UPLOAD 128
ENV PHP_MAX_POST 128M</blockquote>
WORKDIR /var/www/auto6
RUN pwd