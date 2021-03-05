# Application image
#
# This image mainly adds the latest application source to the base image
#
FROM wordpress:latest

COPY . /var/www/html

RUN chown -R www-data:www-data /var/www/html
