Ansible Role | DirectAdmin
=========

[![Build Status](https://travis-ci.org/rlunar/directadmin.svg?branch=master)](https://travis-ci.org/rlunar/directadmin)

Deploy [DirectAdmin](https://directadmin.com/) with Ansible

Original [hyperized/ansible-directadmin](https://github.com/hyperized/ansible-directadmin)

Requirements
------------

- A DirectAdmin license is required.
- A clean machine is required. DirectAdmin will actively overwrite existing packages.
- A publicly reachable IP is required.
- Root access to the target machine is required. For details, read: [Step 3](https://www.directadmin.com/installguide.php)

Ansible 2.1 is highly recommended.

Role Variables
--------------

Its recommended that you use either the `group_vars` / `host_vars` to set the required variables per server:

    directadmin_client_id:
    directadmin_license_id:
    directadmin_hostname: # Optional, will be obtained from server
    directadmin_ip_address: # Optional, will be obtained from server

If you wish to use a custom custombuild configuration, please configure:

    directadmin_custombuild_options_conf: http://yourdomain.com/options.conf

Dependencies
------------

As of present there are no dependent roles. (They may be added later)

Recommended to have installed on your server are:

    - Firewall
    - SSH protection (Fail2Ban)
    - Kernel hardening

FreeBSD support may be added later.

Example Playbook
----------------

    - hosts: servers
      become: yes
      roles:
         - { role: webdcg.directadmin }

License
-------

MIT

Author Information
------------------

Roberto Luna <roberto.luna.rojas@gmail.com>

Original package
Gerben Geijteman <gerben@hyperized.net>
