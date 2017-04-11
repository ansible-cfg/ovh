Role Name
=========

This role reinstalls OVH VPS instances, resets ssh fingerprints and wait for the server to be up.

Requirements
------------

My OVH custom module must be present in the `library` folder of your playbooks root location : https://github.com/udbellamy/ovh-module

Role Variables
--------------

You must set the following variables for this role to work :

    appkey: # Application Key provided with your ovh application
    appsecret: # Application Secret Key provided with your ovh application
    consumerkey: # Consumer key provided when you have manually generated a valid token to POST and GET
    ssh_keys: 
      - # Name of ssh key 1 to add
      - # Name of ssh key 2 to add etc..

The variable `service` must be set at the playbook level.

Example Playbook
----------------

    - hosts: all
      tasks:
        - name: Set service name
          set_fact:
            service: "{{ ansible_fqdn }}"

    - hosts: all
      connection: local
      roles: 
        - ovh

License
-------

GPLv2

Author Information
------------------

[¬º-°]¬
