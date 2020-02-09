Role Name
=========

jenkins

[![Build Status](https://travis-ci.org/cmihai-ansible/jenkins.svg?branch=master)](https://travis-ci.org/cmihai-ansible/jenkins)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.jenkins](https://galaxy.ansible.com/devopstoolbox.jenkins)

```bash
ansible-galaxy install devopstoolbox.jenkins
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```yaml
jenkins_service_port: 8081
jenkins_display_admin_password: true
jenkins_enable_service: true
jenkins_enable_selinux: true
jenkins_copy_templates: true
jenkins_firewall_configure: true
jenkins_firewall_rules:
  - port: 8081
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install jenkins on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: jenkins is configured
      import_role:
        name: devopstoolbox.jenkins
      vars:
        jenkins_service_port: 8081
        jenkins_display_admin_password: true
        jenkins_enable_service: true
        jenkins_enable_selinux: true
        jenkins_copy_templates: true
        jenkins_firewall_configure: true
        jenkins_firewall_rules:
          - port: 8081
      tags: jenkins
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/crivetimihai)
