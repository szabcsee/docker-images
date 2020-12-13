# Application image
#
# This image mainly adds the latest application source to the base image
#
FROM szabcsee/yii2-php:7.1-apache

RUN apk --no-cache add curl \
    && apk --no-cache add php-curl \
    && apk add --no-cache php7-simplexml \
    && apk add --no-cache composer \
    && apk add --no-cache beanstalkd
# Copy the app code into the image
COPY . /var/www/html

# Create required directories listed in .dockerignore
RUN mkdir -p runtime web/assets var/sessions \
    && chown www-data:www-data runtime web/assets var/sessions \
    && beanstalkd -l 127.0.0.1 -p 11300 &
# Let docker create a volume for the session dir.
# This keeps the session files even if the container is rebuilt.
VOLUME /var/www/html/var/sessions
