FROM php:5-apache
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install mysql
    #&& docker-php-ext-install mysqli
RUN apt-get install -y git

#run the git from the naflm master branch
RUN git clone https://github.com/TheNAF/naflm.git /var/www/html/

#images need to be writable by the webserver.
RUN chmod g+w /var/www/html/images
RUN chmod a+w /var/www/html/images

#Put in the defulat settings.php file to match the docker images
COPY settings.php /var/www/html/.