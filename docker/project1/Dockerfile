FROM php:8.2-fpm

# Install dependencies
RUN apt-get update && apt-get install -y \
    nano \
    vim \
    npm \
    git \
    zip \
    unzip \
    && docker-php-ext-install pdo pdo_mysql

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer


# Set working directory
WORKDIR /var/www/html

# Install Node.js and NPM
RUN npm install -g npm@latest

EXPOSE 9000
