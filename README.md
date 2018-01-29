Install fail2ban [![Build Status](https://travis-ci.org/shengyou/ansible-role-fail2ban.svg?branch=master)](https://travis-ci.org/shengyou/ansible-role-fail2ban)
=========

安裝 fail2ban。

Requirements
------------

* ansible >= 2.4
* python >= 2.6

Role Variables
--------------

以下四種 Variables 非必填項目，想要設定客製的 fail2ban config 才需要設置。

使用方式請參考範例。

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
