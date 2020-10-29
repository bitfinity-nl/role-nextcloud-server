# role-nextcloud-server
=========

This role contains the installation steps to setup a Nextcloud server with OnlyOffice.

Requirements
------------

This role supports:
- Ubuntu 20.04;

This role requires:
- Ubuntu 20.04;
- MySQL/MariaDB already installed (bitfinity-nl/role-certbot-apache2);
- Letsencrypt certificate already installed (bitfinity-nl/role-mariadb-server-10.5 );

Required steps:
1. Register the (sub)domain; 
2. Ensure port 80 and 443 are open on the server and firewall (configure HAProxy for TCP ports);
3. Add the role to your playbook;
4. Override the defaults or in the playbook;

Role Variables
--------------

See defaults/main.yml for more information.

Dependencies
------------

See defaults/main.yml for more information.

Example Playbook
----------------

For adding additional domain controller use the example below

    - hosts: nextcloud
      become: yes

      vars:
        #-- Custom settings: role-nextcloud-server --
        nc_mariadb_user       : 'nextcloud'
        nc_mariadb_pass       : 'ChangeMe'
        nc_nextcloud_admin    : 'sysadmin'
        nc_nextcloud_pass     : 'Password'  
        nc_nextcloud_domain   : 'test.bitfinity.nl'
        
      roles:
        - role-nextcloud-server

License
-------

GPLv3

Author Information
------------------

I: https://www.bitfinity.nl \
E: info@bitfinity.nl

