FROM php:8.3-fpm

# Instalar dependencias del sistema necesarias
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    curl \
    libicu-dev \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    mariadb-client \
    && docker-php-ext-install \
        pdo \
        pdo_mysql \
        mysqli \
        intl \
        zip \
        bcmath \
        gd \
        mbstring \
        xml \
    && docker-php-ext-enable pdo_mysql

# Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

# Directorio de trabajo
WORKDIR /application
