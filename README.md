#Observium
=========

Ansible role to manage [Observium](https://www.observium.org/), a network
monitoring platform.

Observium is a low-maintenance auto-discovering network monitoring
platform supporting a wide range of device types, platforms and
operating systems.

It is licensed under the *Observium Professional License*, a simplified
version of the QPL.  See: https://observium.org/docs/licenses/

##Requirements
------------

There are no external dependencies.

##Role Variables
--------------

For now, pleae refer to the variables documented in *defaults/main.yml*.

##Dependencies
------------

There are no dependencies on other roles.

##Example Playbook
----------------

A trivial example:
```
    - hosts: nms
      roles:
        - role: observium
      become: true
      vars:
        observium_db_pass: observium
        observium_path: /opt/observium
        observium_type: Community # Community or  Subscription
        rrdcached_socket: /var/run/rrdcached.sock
        rrdcached_basefolder: "{{ observium_path }}/rrd"
        smokeping_datadir: "{{ rrdcached_basefolder }}/smokeping"
        apache_group: www-data
  ```     
The variables liste above some of the variables that are shared between the different programs, and are more importen.

##License
-------

MIT

##Author Information
------------------

See https://github.com/eideen
