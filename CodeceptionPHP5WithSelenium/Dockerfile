FROM anapsix/alpine-java:8

MAINTAINER nootan.ghimire@gmail.com

RUN apk update \
    && apk add php5 \
    && apk add openssl

RUN mkdir -p /usr/local/bin

RUN wget http://goo.gl/dR7Lg2
RUN mv dR7Lg2 /usr/local/bin/selenium-server-standalone-3.2.0.jar

RUN wget http://codeception.com/codecept.phar
RUN mv codecept.phar /usr/local/bin/codecept

RUN wget http://getcomposer.org/composer.phar
RUN mv composer.phar /usr/local/bin/composer.phar

RUN wget http://github.com/mozilla/geckodriver/releases/download/v0.15.0/geckodriver-v0.15.0-linux64.tar.gz
RUN tar -xzf geckodriver-v0.15.0-linux64.tar.gz
RUN mv geckodriver /usr/local/bin/geckodriver

RUN java -jar /usr/local/bin/selenium-server-standalone-3.2.0.jar & 

EXPOSE 8080 4444
