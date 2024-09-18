![89d0d8274647c3b962cbb83bd5b0125a](https://github.com/user-attachments/assets/900d05b3-18d5-44e0-95df-35c2c13b34cb)

# ----------------------
# The FPM base container
# ----------------------
FROM php:7.4-fpm-alpine AS dev
FROM php:8.2-fpm-alpine AS dev

RUN apk add --no-cache --virtual .build-deps \
    $PHPIZE_DEPS \
    freetype-dev \
    libpng-dev \
    postgresql-dev

# Cleanup apk cache and temp files
RUN rm -rf /var/cache/apk/* /tmp/*

# Configure php extensions
RUN docker-php-ext-configure gd --with-freetype

# Install php extensions
RUN docker-php-ext-install \
    gd \
    pdo \
    pdo_pgsql

# Cleanup apk cache and temp files
RUN rm -rf /var/cache/apk/* /tmp/*

# ----------------------
# Composer install step
# ----------------------

# Get latest Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# ----------------------
# The FPM production container
# ----------------------
FROM dev
# ----------------------
# The FPM base container
# ----------------------
FROM php:7.4-fpm-alpine AS dev
FROM php:8.2-fpm-alpine AS dev

RUN apk add --no-cache --virtual .build-deps \
    $PHPIZE_DEPS \
    freetype-dev \
    libpng-dev \
    postgresql-dev

# Cleanup apk cache and temp files
RUN rm -rf /var/cache/apk/* /tmp/*

# Configure php extensions
RUN docker-php-ext-configure gd --with-freetype

# Install php extensions
RUN docker-php-ext-install \
    gd \
    pdo \
    pdo_pgsql

# Cleanup apk cache and temp files
RUN rm -rf /var/cache/apk/* /tmp/*

# ----------------------
# Composer install step
# ----------------------

# Get latest Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# ----------------------
# The FPM production container
# ----------------------
FROM dev

{
    "_readme": [
        "This file locks the dependencies of your project to a known state",
        "Read more about it at https://getcomposer.org/doc/01-basic-usage.md#installing-dependencies",
        "This file is @generated automatically"
    ],
    "content-hash": "c195f74d31d50551002e9d651d866d6a",
    "content-hash": "b00842ff96e3874eb5628c80ae18f6ce",
    "packages": [
        {
            "name": "badges/poser",
            "version": "v2.3.1",
            "version": "v3.1.0",
            "source": {
                "type": "git",
                "url": "https://github.com/badges/poser.git",
                "reference": "13f4ae7998700568fe1d07c8964492ea845e675c"
                "reference": "6bc1998ad98e10ad7d16f2b0784a286c105d7991"
            },
            "dist": {
                "type": "zip",
                "url": "https://api.github.com/repos/badges/poser/zipball/13f4ae7998700568fe1d07c8964492ea845e675c",
                "reference": "13f4ae7998700568fe1d07c8964492ea845e675c",
                "url": "https://api.github.com/repos/badges/poser/zipball/6bc1998ad98e10ad7d16f2b0784a286c105d7991",
                "reference": "6bc1998ad98e10ad7d16f2b0784a286c105d7991",
                "shasum": ""
            },
            "require": {
                "cybercog/php-svg-font": "^1.0",
                "ext-gd": "*",
                "ext-simplexml": "*",
                "kartsims/easysvg": "^2.4",
                "php": ">=7.4",
                "symfony/console": "^4.0|^5.0|^6.0"
                "kartsims/easysvg": "^2.5",
                "php": "^8.1",
                "symfony/console": "^5.0 || ^6.0 || ^7.0"
            },
            "require-dev": {
                "behat/behat": "^3.8",
                "friends-of-phpspec/phpspec-code-coverage": "^6.0",
                "friendsofphp/php-cs-fixer": "^3.5",
                "behat/behat": "^3.13",
                "friends-of-phpspec/phpspec-code-coverage": "^6.3",
                "friendsofphp/php-cs-fixer": "^3.41",
                "moave/phpspec-data-provider-extension": "dev-feat/add-compatibility-to-php80",
                "phpspec/phpspec": "^7.0",
                "vimeo/psalm": "^4.3"
                "phpspec/phpspec": "^7.4",
                "vimeo/psalm": "^4.30"
            },
            "bin": [
                "bin/poser"
            ],
            "type": "lib",
            "extra": {
                "branch-alias": {
                    "dev-master": "2.x-dev"
                }
            },
            "autoload": {
                "psr-4": {
                    "PUGX\\Poser\\": "src/"
                }
            },
            "notification-url": "https://packagist.org/downloads/",
            "license": [
                "MIT"
            ],
            "authors": [
                {
                    "name": "Giulio De Donato",
                    "email": "liuggio@gmail.com"
                },


