FROM hhvm/hhvm-proxygen:latest

RUN apt-get update -y && apt-get install -y curl && apt-get clean

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN chmod +x /usr/local/bin/composer

# Install the app
RUN rm -rf /var/www
ADD . /var/www
RUN cd /var/www && /usr/local/bin/composer install

# Reconfigure HHVM
ADD ./docker/hhvm/site.ini /etc/hhvm/site.ini

WORKDIR /var/www

EXPOSE 80
