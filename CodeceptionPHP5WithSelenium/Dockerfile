#FROM composer/composer:php5-alpine
FROM anapsix/alpine-java:8

MAINTAINER nootan.ghimire@gmail.com

RUN apk update \
    && apk add php5 php5-phar php5-json \
    && apk add openssl \
    && apk add curl \
    && apk add git

RUN mkdir -p /usr/local/bin
ENV PATH="$PATH:/usr/local/bin"

RUN wget http://goo.gl/dR7Lg2
RUN mv dR7Lg2 /usr/local/bin/selenium-server-standalone-3.2.0.jar

RUN wget http://codeception.com/codecept.phar
RUN mv codecept.phar /usr/local/bin/codecept
RUN chmod +x /usr/local/bin/codecept

RUN wget http://getcomposer.org/composer.phar
RUN mv composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer

# Composer --needs openssl (FIXME [by installing openssl ext])
#RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
#RUN php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
#RUN php composer-setup.php
#RUN php -r "unlink('composer-setup.php');"

#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN wget http://github.com/mozilla/geckodriver/releases/download/v0.15.0/geckodriver-v0.15.0-linux64.tar.gz
RUN tar -xzf geckodriver-v0.15.0-linux64.tar.gz
RUN mv geckodriver /usr/local/bin/geckodriver

RUN composer --version

EXPOSE 8080 4444
