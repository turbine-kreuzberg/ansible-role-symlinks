Ansible Role: votum.symlinks
============================
[![Build Status](https://travis-ci.org/votum/ansible-role-symlinks.svg?branch=master)](https://travis-ci.org/votum/ansible-role-symlinks)

Role for turning existing directories into symlinks. 
Usefull for preparing capistrano style deployments.

Requirements
------------

none

Role Variables
--------------

Use `symlinks_directory_symlink_dict` to describe your symlinks as shown in the example playbook below.

Dependencies
------------

none

Example Playbook
----------------

    - hosts: servers
      vars:
        symlinks_directory_symlink_dict:
          - { directory: '/var/www/foo/releases/00000000000000', symlink: '/var/www/foo/current' }
          - { directory: '/var/www/foo/shared/common', symlink: '/var/www/foo/releases/00000000000000/common' }
          - { directory: '/var/www/foo/shared/media', symlink: '/var/www/foo/releases/00000000000000/media' }
          - { directory: '/var/www/foo/shared/log', symlink: '/var/www/foo/releases/00000000000000/var/log' }
      roles:
         - { role: votum.symlinks }

License
-------

MIT

Author Information
------------------

VOTUM GmbH
