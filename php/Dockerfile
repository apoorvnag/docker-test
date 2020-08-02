FROM phalconphp/php:7.1-min
FROM phalconphp/php-fpm:7.2-min

RUN apt-get update && apt-get install -y zlib1g-dev libpng-dev git && docker-php-ext-install zip
RUN docker-php-ext-install pdo_mysql 
RUN pecl install redis && echo "extension=redis.so" >> /usr/local/etc/php/conf.d/phalcon.ini
RUN docker-php-ext-install gd 

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer
RUN php -r "unlink('composer-setup.php');"

RUN apt-get update && apt-get install -y python-setuptools 
RUN easy_install supervisor