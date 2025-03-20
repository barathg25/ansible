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

# Ansible adhoc command

ansible -m ping all                     -- to ping tha all servers.

ansible servers -m ping                 -- to ping the specfic server group.

ansible servers -m command -a "shutdown"  -- to stop all slave server

ansible servers -m command -a “df -hk”    -- to run the linux command.

ansible servers -m apt -a “name=nginx state=present”-- to install nginx in servers .

ansible servers -m apt -a “name=nginx state=absent” --  to remove the nginx in servers .

ansible servers -m service -a “name=nginx state=restarted”   --  to restart the nginx in webservers.

ansible servers -m shell -a “ps -ef | wc -l”   --   to  use the  pipe command.

ansible servers -m copy -a "src=/home/ubuntu/file.txt dest=/home/ubuntu"    --  to copy the files master intonodes(servers).

ansible servers -m fetch -a "src=/home/ubuntu/test.txt dest=/home/ubuntu/"  --  to fetch(pull)  the files remote server into ansible mastre server.

ansible server -m file -a  “dest=/home/ubuntu/demo mode=666 state=directory” -- to create the direcctory in remote server.

ansible-playbook demo.yml  --syntax-check

