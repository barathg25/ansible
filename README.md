# ansible


1 . Install Ansible
# To connect Multiple Servers with Ansible
2 . Generate ssh key in Ansible server # ssh-keygen    
cp the key from .ssh/.pub  to The host server to .ssh/authoriesd key

3 . to check the connectivity    ssh ubuntu@IP Address

4 . To communicate with Ansible

Add ip in vi /etc/ansible/hosts
# 
[servers]
server1 ansible_host=52.66.250.0 (slave-server ip)
server2 ansible_host=42.46.50.20 (slave-server  ip)
[all:vars]
ansible_python_interpreter=/usr/bin/python3

