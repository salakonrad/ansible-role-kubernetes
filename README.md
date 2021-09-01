# Ansible role for k8s 3 node install 
### Create the install.yml playbook
```
---
- hosts: k8s-nodes
  become: yes
  roles:
    - ansible-k8s
```  
### Setup SSH Config file
- Execute `vagrant ssh-config >> ~/.ssh/config`

### Create kubernetes.inventory and Type in your Addresses
- Create kubernetes.inventory
```
[k8s-nodes]
node1 ansible_host=node1 ansible_port=2222 role=master
node2 ansible_host=node2 ansible_port=2200 role=worker
node3 ansible_host=node3 ansible_port=2201 role=worker
```

### Execute Ansible role
sudo password for vagrant user is `vagrant`
```
ansible-playbook -i kubernetes.inventory install.yml --ask-become-pass
```
