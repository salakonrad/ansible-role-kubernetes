# Ansible role for k8s 3 node install 
Create the install.yml playbook
```
---
- hosts: all
  roles:
    - ansible-kubernetes
  become: yes
```  
Create kubernetes.inventory and Type in your Adresses
```
node1 ansible_host=192.168.56.10 ansible_port=22 role=master
node2 ansible_host=192.168.56.11 ansible_port=22 role=worker
node3 ansible_host=192.168.56.12 ansible_port=22 role=worker
```

Execute Ansible role
```
ansible-playbook -i kubernetes.inventory install.yml
```