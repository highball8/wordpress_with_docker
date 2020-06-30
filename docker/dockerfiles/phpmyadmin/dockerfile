# phpMyAdmin Dockerfile: Create container from official phpmyadmin/phpmyadmin:latest image, update, and replace php.ini file.
# docker build -t phpmyadmin_local:phpmyadmin_custom_1.0 .

FROM phpmyadmin/phpmyadmin:latest

# APT Update/Upgrade, then install packages we need
RUN apt update && \
    apt upgrade -y && \
    apt autoremove && \
    apt install -y \
    vim

# Replace php.ini
COPY php.ini /usr/local/etc/php

# Remove old php.ini files
RUN rm /usr/local/etc/php/php.ini-development && \
    rm /usr/local/etc/php/php.ini-production