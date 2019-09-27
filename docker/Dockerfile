FROM php:7.3-alpine

MAINTAINER mitake <mitake.ck@gmail.com>

# install composer 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install phpcs
RUN curl -L https://squizlabs.github.io/PHP_CodeSniffer/phpcs.phar > /usr/local/bin/phpcs
RUN chmod +x /usr/local/bin/phpcs

# install cakephp rule for phpcs
RUN composer global require cakephp/cakephp-codesniffer
RUN phpcs --config-set installed_paths /root/.composer/vendor/cakephp/cakephp-codesniffer
RUN phpcs --config-set default_standard CakePHP

VOLUME ["/src"]
WORKDIR /src

ENTRYPOINT ["phpcs"]
