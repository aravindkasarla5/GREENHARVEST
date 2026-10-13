FROM php:8.2-apache

RUN docker-php-ext-install pdo pdo_mysql mysqli

RUN a2enmod rewrite

RUN rm -f /etc/apache2/mods-enabled/mpm_event.conf /etc/apache2/mods-enabled/mpm_event.load /etc/apache2/mods-enabled/mpm_worker.conf /etc/apache2/mods-enabled/mpm_worker.load

WORKDIR /var/www/html
COPY . /var/www/html/

RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html && chmod -R 777 /var/www/html/uploads 2>/dev/null || true

EXPOSE 80

CMD ["apache2-foreground"]
