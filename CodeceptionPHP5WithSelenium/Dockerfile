FROM debian:jessie-backports

MAINTAINER nootan.ghimire@gmail.com

RUN apt-get update \
    && yes | apt-get install openssl curl php5  php5-json php5-curl git default-jre default-jdk wget


RUN mkdir -p /usr/local/bin
ENV PATH="$PATH:/usr/local/bin"

RUN wget http://goo.gl/dR7Lg2 -o /usr/local/bin/selenium-server-standalone-3.2.0.jar \
    && wget http://codeception.com/codecept.phar -o /usr/local/bin/codecept \
    && chmod +x /usr/local/bin/codecept \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && wget http://github.com/mozilla/geckodriver/releases/download/v0.15.0/geckodriver-v0.15.0-linux64.tar.gz \
    && tar -xzf geckodriver-v0.15.0-linux64.tar.gz \
    && mv geckodriver /usr/local/bin/geckodriver

#RUN composer --version
#RUN java -jar /usr/local/bin/selenium-server-standalone-3.2.0.jar &

EXPOSE 8080 4444
