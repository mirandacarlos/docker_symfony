FROM php:8-fpm
RUN apt-get update && apt-get install -y libicu-dev git zip
RUN mv $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini
RUN docker-php-ext-configure intl \
&& docker-php-ext-install intl opcache
RUN pecl install -f xdebug && docker-php-ext-enable xdebug 
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony
COPY --from=composer /usr/bin/composer /usr/local/bin/composer