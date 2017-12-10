Install fail2ban
=========

安裝 fail2ban。

Requirements
------------

* ansible >= 2.4
* python >= 2.6

Role Variables
--------------

* custom_jail_conf
* custom_filters
* custom_actions
* custom_jails


Dependencies
------------

none.

Example Playbook
----------------

```
- name: install_fail2ban.yml
  hosts: myhost
  gather_facts: yes
  become: yes

  vars:
   - custom_jail_conf: /path/to/conf/filename
   
   - custom_filters::
       - src: /path/to/filters
         filename: filter_filename.conf
       - src: /path/to/filters
         filename: filter_filename.conf

   - custom_actions:
      - src: /path/to/actions
        filename: action_filename.conf
      - src: /path/to/actions
        filename: action_filename.conf

   - custom_jails:
      - src: /path/to/jails
        filename: jail_filename.conf
      - src: /path/to/jails
        filename: jail_filename.conf

  roles:
    - install_fail2ban
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
