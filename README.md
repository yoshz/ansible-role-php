# php

Ansible role which installs and configures PHP.

## Requirements

- Tested on Ansible 1.5
- Tested on Ubuntu 14.04 (trusty), but it should work on any modern Debian based system.

## Dependencies

None.

## Example playbook

To use this role, build a vars file (vars/php.yml, for example) which you include in your playbook,
which contains something like the following:

    php_webserver: apache2

    php_cli_config:
      max_execution_time: 0

    php_apache_config:
      max_execution_time: 20

    php_extensions:
      - php5-gd
      - php5-mysql
      - php5-pgsql

    php_pecl_extensions:
      - mongo

    php_pear_channels:
      - pear.phpunit.de

    php_pear_packages:
      - phpunit/phpunit

Next, you can include the role in your playbook:

    - hosts: all
      sudo: yes
      vars_files:
        - vars/php.yml
      roles:
        - php

There are a lot of config settings you can overwrite, but you'll have to refer to the files
`defaults/main.yml` to see a list of variables and their description.

## Licence

MIT