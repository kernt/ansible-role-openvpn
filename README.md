Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Configure EasyRSA manuelly
--------------------------

```s
easyrsa init-pki
PATH=$PATH:/usr/share/easy-rsa/3.0.3/
easyrsa init-pki
easyrsa build-ca
easyrsa gen-dh
easyrsa gen-req server nopass
easyrsa sign-req server server
easyrsa gen-req client nopass
easyrsa sign-req client client

openssl dhparam -out /etc/openvpn/dh2048.pem 2048

```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

## Quellen

* [rsa-key-management](https://openvpn.net/community-resources/rsa-key-management/)
* [Ansible role for easy_rsa](https://github.com/kernt/easy_rsa)
* [openvpn ansible role example for loops](https://github.com/stackhpc/ansible-role-openvpn/blob/master/tasks/main.yml)
* [easy-rsa quickstart](https://github.com/OpenVPN/easy-rsa/blob/master/README.quickstart.md)
