# Ansible Role: Composer

[![Build Status](https://img.shields.io/travis/rwanyoike/ansible-role-composer.svg)](https://travis-ci.org/rwanyoike/ansible-role-composer) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/rwanyoike/ansible-role-composer/master/LICENSE)

Installs and configures Composer on RHEL/CentOS ~~or Debian/Ubuntu~~.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
composer_self_update: false
composer_exec: /usr/local/bin/composer
# The directory where global packages will be installed
composer_home_dir: ~/.composer
composer_add_to_path: true
# GitHub OAuth token (used to help overcome API rate limits)
composer_github_oauth_token: ""
# A list of packages to install globally. See commented examples below for
# usage; the 'release' is optional, and defaults to '@stable'
composer_global_packages: []
```

## Dependencies

- rwanyoike.php (https://github.com/rwanyoike/ansible-role-php)

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: rwanyoike.composer
```

Inside `vars/main.yml`:

```yaml
composer_self_update: true
composer_global_packages:
  - name: phpunit/phpunit
    release: "@stable"

# ... etc ...
```

## License

MIT

## Author Information

- This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
- This role was forked in 2015 by [Raymond Wanyoike](https://github.com/rwanyoike).
