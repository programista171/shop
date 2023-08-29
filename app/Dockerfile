FROM php:7.4-fpm

# Instalacja dodatkowych narzędzi i rozszerzeń PHP
RUN apt-get update && apt-get install -y \
    libicu-dev \
    zip \
    unzip \
    && docker-php-ext-install -j$(nproc) intl pdo pdo_mysql

# Instalacja Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html

CMD ["php-fpm"]

EXPOSE 9000
