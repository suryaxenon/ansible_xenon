# ansible
---
- hosts: ubuntu
  user: ansible
  become: yes
  connection: ssh
  tasks:
    - name: uninstall mysql on AMI linux
      apt: name={{ item }} state=absent
      with_items:
        - mysql-community-server
        - mysql-community-client
        - MySQL-python
