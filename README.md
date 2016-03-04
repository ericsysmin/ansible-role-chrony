chrony
===

This role enables users to install and configure chrony on their hosts.

Build Status
------------
[![Build Status](https://travis-ci.org/ericsysmin/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/ericsysmin/ansible-role-chrony)

Requirements
------------

This role requires Ansible 1.4 or higher.

Examples
--------

1) Install chrony and use the default settings.

	- hosts: all
	  roles:
	    - role: chrony

2) Install chrony and use custom servers.

	- hosts: all
	  roles:
	    - role: chrony
	      chrony_config_server: [0.pool.ntp.org, 2.pool.ntp.org]

License
-------

GPLv2

Author Information
------------------

- Eric Anderson