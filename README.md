# ansible-role-mgt-usergrp
This role is create user/group.   

# variable
You can will change variable.
   
* `tests/userlist.yml`   
```yaml
---
group_list:
    - grp_name: demogrp
      gid: 777

user_list:
    - id: demouser
      new_password: 6af286f0509e7c166abf710850f44fc4
      uid: 777
      groups: demogrp
      comment: "KR/ANSIBLE/DEMO/USER/"
```
   
# playbook
This is example playbook.   
```yaml
---
- name: management 'user'
  hosts: node
  vars_files:
    - userlist.yml
  roles:
  - role: ansible.role-mgt-usergrp
```
   
* example inventory   
```yaml
[node]
192.168.10.10
   
[node:vars]
ansible_ssh_user=root
ansible_ssh_pass=testtest
```
   
# How to use roles?
As follows run commands.

```bash
$ cd /etc/ansible/roles
$ git clone https://github.com/chhanz/ansible.role-mgt-usergrp.git
