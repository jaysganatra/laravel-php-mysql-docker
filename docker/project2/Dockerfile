FROM php:8.1-fpm

# Install dependencies
RUN apt-get update && apt-get install -y \
    nano \
    vim \
    npm \
    git \
    zip \
    unzip

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer


# Set working directory
WORKDIR /var/www/html

# Install Node.js and NPM
RUN npm install -g npm@latest

EXPOSE 9000
