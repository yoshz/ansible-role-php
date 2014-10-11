php
===

An Ansible role for installing and configuring PHP on Ubuntu Trusty with support for Apache2, PHP-FPM, PEAR and PECL.


Requirements
------------

- Ubuntu Trusty
- Nginx or Apache should be installed


Role Variables
--------------

See `defaults/main.yml` for a list of variables.

Examples:

    php_webserver: apache2

    php_cli_config:
      max_execution_time: 0

    php_apache_config:
      max_execution_time: 20

    php_packages:
      - php5-xdebug
      - php5-mysql

    php_extensions:
      - mysql

    php_pecl_extensions:
      - mongo

    php_pear_channels:
      - pear.phpunit.de

    php_pear_packages:
      - phpunit/phpunit


It is also possible to configure PHP-FPM:

    php_webserver: php5-fpm

    php_fpm_pool_config:
      user: vagrant
      group: vagrant
      listen.owner: vagrant
      listen.group: vagrant
    

Dependencies
------------

None


Licence
-------

MIT
