Ansible Project



1.docker run -dit -p 81:80 --privileged --name machine-1 ubuntu
2.docker run -dit -p 82:80 --privileged --name machine-2 ubuntu
3.docker run -dit -p 83:80 --privileged --name machine-3 ubuntu


apt-get update -y
apt-get upgrade -y
apt-get install iputils-ping -y
apt install openssh-client -y && apt install openssh-server -y
ifconfig
ssh-keygen
touch .ssh/authorized_keys
chmod  700 .ssh && chmod  600 .ssh/authorized_keys
cat .ssh/id_rsa.pub
vi .ssh/authorized_keys
apt install vim
vi .ssh/authorized_keys
sudo /etc/init.d/ssh restart
sudo /etc/init.d/ssh status
apt install apache2
sudo /etc/init.d/apache2 status
sudo /etc/init.d/apache2 start
apt install ansible -y 
=============================

vi /etc/ansible/hosts

[servers]
172.17.0.3
172.17.0.4

[servers:vars]
ansible_user=root

=========================

vi /etc/ansible/ansible.cfg

host_key_cheking = False

===============================
ansible servers -m ping
ansible servers -a "cat /etc/os-release"
ansible servers -a "apt install apache2 -y"
ansible servers -a "sudo /etc/init.d/apache2 start"





