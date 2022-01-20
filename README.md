Ansible Project

#e1fa2aa69b0e-Machine-3-172.17.0.4
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCzWJZFLU4nFT9HjSWHvSYK3pUzdgwAYfwdjxbO17QlCfrNSE2N47zI4tuMuqhY5zY7DUJdupb0dhow+CZZzhCt0QoVF/u5paANqIAuycJVwHahLDTAjdIZYVFL5r6DpWnToBoINNoEVNyulUbmiTOEB4130LfHq1+5gfVhY/u5AEU2tAYQGyHkmZLOIWSraREp6rnQF/2kR5Dd7Ownli/9xMN/4NvftYWShaPl0RBFsjcjW+V3tPhTJt0S2yYahyId5sAvRzWN4gwC08RrAiq+09QUwfUPEmo+iEq2cGm/9zFxTpFfyvqPP5wiZewWbejeLTKLLL273YOaCdgCdQzcWXBSob4N+YLS4Fi5m4cdT0v/Nk6ghNRJUhVZn2E8XdtLCTHgfu1RtsnRyDPrd+1Nlp9AJtBNFF0Jag6A1diAVSfcWW3eq1teZ/rCVLtq8La+oy7d41xciG4n9CfeqPmj4wonndVCFmJAJxZo8VqyR7I4rBIGTcHi7ks5yPylOdM= root@e1fa2aa69b0e

#c09175dcde1c-Machine-1-172.17.0.2
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCr2WFflNkhe+5+F8dBHzQCYyKb3M72HGjsgbtgtFXZSO+ziutHvRtO/7Z/RD1k1yN6m2rYS5jlwoOiyrsXqC59+arkLOcFfDA0PnsGcxEmEzscngbqFfZZDh2HfEuN6Kj7vtzsJQzHD2ksZfpClNsV4uGRLmKmYYKlC7ZSerqcHqH/1g0ao8V7RV4Q6pSDB2m3d0lDQZhsyOPdAc9SUDNoum/Il/ImbHBINbRZZL8VRz8UuuH32olOi+yf2rU6l97kUGCOejv5/ZeCmeRVrkX8MGobq1DEULoA7b+knffkpunn2rLj3Ic9UQ5zP1yd+VXMkYDMPFISX5+m4bJFF+ipmTaAkN2Un9IFWSkg2GiVJHs4WaQrnA0PtSS+iF55KnTh1PyZSVtvz553uxjgSCD3zQS0k1jG6GMvxbqNhInoZFuNeX2XNyxmE4Uk7kHtGLJ6ilo3e52S0mMCpULC9hG97hM5Tl6iuWOve/qEI6kH3P9ZH4lEH8EzfKqWDa+NrBs= root@c09175dcde1c

#f1568eaee5c9-Machine-2-172.17.0.3
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCdtJdwSekve9LghUQHdGl6MRywS2GBhmPhk3NiOtYkqHwM466jagGWzIn/SamZKt5k6M76oVBuww+rnkoUutTEkTiCegYujgu85fpGRtddR63qWcSGNwBaX+cu8xsEDz9StA8OeDY3xx4G4jzYo5rT0biU+GOarN8ImHzzGhf5fo2p39YyvA/3qYZg7CkV70NuNhAGa1JaElDFQcE1ZAexIZl/wXBWoQZeVPhqdT/xvBRexbFLgTsDGCvosLhC7UoQZD9UV4OZ5SCgGZjpucUfdNXyyOhjYurCG94sN3lrqc6UcEuGMioyfhG0LqnE0/E7d14Oda7aoqnCZigr7UrjyIihxVCWlcM+Yz4j9CjYgNQbYhmIA7fdXNpQiG+P5Q8uwA6L5aEQhz3aPHuTCW97XsK9+gaUioSzf5vJ40ebd6d8Au8UaurvRh0AuHLkJdP7aZpPLFuE1eI+COQsmj6TmgK8yfydsv1emCu99znvKAZM2es5B+IpIKwwGi15oAk= root@f1568eaee5c9


docker pull ubuntu
docker run -dit -p 81:80 --privileged --name machine-1 ubuntu
docker run -dit -p 82:80 --privileged --name machine-2 ubuntu
docker run -dit -p 83:80 --privileged --name machine-3 ubuntu


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

esc :wq!
=========================

vi /etc/ansible/ansible.cfg

host_key_cheking = False

esc :wq!
===============================
ansible servers -m ping
ansible servers -a "cat /etc/os-release"
ansible servers -a "apt install apache2 -y"
ansible servers -a "sudo /etc/init.d/apache2 start"





