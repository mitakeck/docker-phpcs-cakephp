FROM php:7.3-alpine

MAINTAINER mitake <mitake.ck@gmail.com>

ENV PHPCS_VERSION=3.5.0

# install composer 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install phpcs
RUN curl -L https://github.com/squizlabs/PHP_CodeSniffer/releases/download/${PHPCS_VERSION}/phpcs.phar > /usr/local/bin/phpcs && \
  chmod +x /usr/local/bin/phpcs

# install cakephp rule for phpcs
RUN composer global require cakephp/cakephp-codesniffer && \
  phpcs --config-set installed_paths /root/.composer/vendor/cakephp/cakephp-codesniffer && \
  phpcs --config-set default_standard CakePHP

VOLUME ["/src"]
WORKDIR /src

ENTRYPOINT ["phpcs"]
