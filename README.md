# PHP Roles Collection for Ansible

[![Build Status](https://travis-ci.com/geerlingguy/ansible-collection-php_roles.svg?branch=master)](https://travis-ci.com/geerlingguy/ansible-collection-php_roles)

This collection contains all the PHP-related roles maintained by Jeff Geerling (geerlingguy).

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

Install this collection locally:

    ansible-galaxy collection install geerlingguy.php_roles -p ./collections

Then you can use the roles from the collection in your playbooks:

    ---
    - hosts: all
    
      collections:
        - geerlingguy.php_roles
    
      roles:
        - php
        - role: php-versions
          vars:
            php_version: '7.3'

> If you want to be more explicit, you can use the fully-qualified role name when referring to a role in this collection, like `geerlingguy.php_roles.php` instead of just `php`. This could be helpful if, for example, you maintain a separate `php` role in another place on your local workstation.

## Development

Currently, all the PHP roles (inside `roles/`) are Git submodules, and work on the roles themselves should take place in the upstream Role repository. At some point, the roles might move into this repository for their canonical home.

This collection has some integration tests (inside `test/`), however, which pull all the roles together and ensure they work in tandem on the latest supported platforms.

The integrated tests use `ansible-test`. You can run them with the following command:

    ansible-test integration --docker geerlingguy/docker-ubuntu1804-ansible

> Note: You can switch out `ubuntu1804` with any other supported operating system (e.g. `centos7`).

### Pushing a new version

Currently the process of building and pushing a new version artifact to Galaxy is manual. This process will be automated based on tags/releases via Travis CI soon, but for now, here is how to release a new version:

  1. Update all the git submodules: `git submodule update --recursive --remote`
  1. Push the changes, make sure the CI build is still passing.
  1. If CI passes, update the `version` string in `galaxy.yml` to match the version of the collection you wish to publish.
  1. Tag the new version in the git repository and push it.
  1. Build the collection artifact: `ansible-galaxy collection build`
  1. Publish the collection artifact: `ansible-galaxy collection publish ./geerlingguy-php_roles-1.2.3.tar.gz --api-key=[key goes here]`

> Note: The above commands require Ansible 2.9 or later.

## Author

This collection was created in 2019 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/) and [Ansible for Kubernetes](https://www.ansibleforkubernetes.com).
