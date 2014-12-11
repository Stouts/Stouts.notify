Stouts.notify
=============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.notify.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.notify)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.notify-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/919)

Ansible role which provides an email (jabber, slack) notifications

#### Variables

```yaml
notify_enabled: yes
notify_message: "[{{inventory_hostname}}] has been updated by {{ansible_ssh_user}} on {{ansible_date_time.iso8601}}"

notify_mail_to: ""
notify_mail_cc: ""
notify_mail_from: ansible@{{inventory_hostname}}
notify_mail_host: localhost
notify_mail_port: 25
notify_mail_attach: ""
notify_mail_shell: ""                                         # Copy output from shell command as message body

notify_jabber_to: ""
notify_jabber_user: ""
notify_jabber_host: ""
notify_jabber_port: 5223
notify_jabber_password: ""

notify_slack_webhook: ""
notify_slack_username: ansible
notify_slack_icon: ":rocket:"
notify_slack_channel:
```

#### Usage

Add `Stouts.notify` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
  - Stouts.postfix
  - Stouts.notify

  vars:

    # Setup postfix
    postfix_smtp_sasl_user: myemail@gmail.com
    postfix_smtp_sasl_password: mypassword

    # Setup notify
    notify_mail_to: myemal@gmail.com
    notify_mail_attach: /path/to/changelog

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.notify/issues)!

