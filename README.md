## ansible
sudo apt-get install ansible –y
```
# if ansible repo not on ubuntu version
sudo apt-get update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt-get install ansible –y
```
ssh-keygen -t  # to generate key  
copy the public key to the hosts for performing ssh between the host and master.
```
# depending on ubuntu version ansible directory is created if ansible directory is not created then create one and create one file host and add the ip of nodes
cd /etc
sudo mkdir ansible
cd ansible
sudo vim hosts     # create inventory for host either separate or in groups
```
ansible inventory-name -m ping  #to check connection between master and hosts
```
ansible worker1 -a "mkdir ansible_test" # create directory in inventory worker1
```
ansible -a "pwd"
```
ansible all - a "ls/"
```
ansible all -m ansible.builtin.file -a "dest=/home/ubuntu/ansible_test mode=400"
```
ansible all -m ansible.builtin.file -a "dest=/home/ubuntu/a.txt state=touch"
   ````
   ansible all -a " echo hiiansbile > a.txt "
```
  ansible worker1 -a "sudo apt update"
   ansible worker1 -a "sudo apt install apache2 -y"
```
  ansible worker1 -b -m  ansible.builtin.apt -a "name=apache2 state=latest"
``` 
  vim playbook.yaml
```
ansible-playbook playbook.yaml
 ansible all -a "ls"
 vim nginx.yaml
 ansible-playbook nginx.yaml

