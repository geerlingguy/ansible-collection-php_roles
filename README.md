# PHP Collection for Ansible

This collection is an aggregation of all the PHP-related roles maintained by Jeff Geerling (geerlingguy).

It includes:

  - [geerlingguy.php](https://galaxy.ansible.com/geerlingguy/php)
  - [geerlingguy.php_memcached](https://galaxy.ansible.com/geerlingguy/php-memcached)
  - [geerlingguy.php_mysql](https://galaxy.ansible.com/geerlingguy/php-mysql)
  - [geerlingguy.php_pear](https://galaxy.ansible.com/geerlingguy/php-pear)
  - [geerlingguy.php_pecl](https://galaxy.ansible.com/geerlingguy/php-pecl)
  - [geerlingguy.php_pgsql](https://galaxy.ansible.com/geerlingguy/php-pgsql)
  - [geerlingguy.php_redis](https://galaxy.ansible.com/geerlingguy/php-redis)
  - [geerlingguy.php_tideways](https://galaxy.ansible.com/geerlingguy/php-tideways)
  - [geerlingguy.php_versions](https://galaxy.ansible.com/geerlingguy/php-versions)
  - [geerlingguy.php_xdebug](https://galaxy.ansible.com/geerlingguy/php-xdebug)
  - [geerlingguy.php_xhprof](https://galaxy.ansible.com/geerlingguy/php-xhprof)

## Usage

TODO.

## Development

Currently, all the PHP roles (inside `roles/`) are Git submodules, and work on the roles themselves should take place in the upstream Role repository. At some point, the roles might move into this repository for their canonical home.

This collection has some integration-level tests (inside `tests/`), however, which pull all the roles together and ensure they work in tandem on the latest supported platforms.

The integrated tests use `molecule`, which can be installed via `pip install molecule`.

To build a local test environment and run the tests, run the following command:

    TODO.

## Author

This collection was created in 2019 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/) and [Ansible for Kubernetes](https://www.ansibleforkubernetes.com).
