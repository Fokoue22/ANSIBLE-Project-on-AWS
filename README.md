# ANSIBLE-Project-on-AWS
This repo contain all ansible playbook project for AWS

# Ansible Playbook Project1
Setup an Ansible cluster with the controller running on Amazon Linux 2 and the 4 nodes in which 2 running on Amazon linux and 2 running on ubuntu.

![Alt text](Ansible-ubuntu-controller-1.png)
Write a playbook with four (4) plays:
Play1: Deploy apache on ubuntu clients
Play2: Deploy apache on amazon clients
Play3: Deploy git on amazon linux clients
Play4: Deploy git on ubuntu clients

# STEPS BY STEPS PROCESS 
Launched 3 amazon linux 2 and 2 ubuntu server:
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/652c366e-9281-4c62-ab97-9560917463e8)

Installed ansible on linux-ansible-controller:
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/b44759ac-f49a-4102-acee-deaae6d83818)

Verified ansible is installed in linux-ansible-controller. And generated ssh key-pair. Copied the public key to all 4 nodes:

<img width="512" alt="image" src="https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/088d1bbd-a60b-441e-9b36-99c90b0a2390">

Updated “hosts” file in ansible-controller.
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/ae396a32-ee5a-4d9a-af68-18d0a6fb98ff)

Test the connectivity in-between the controller and nodes:
<img width="590" alt="image" src="https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/dffc2ab1-b43b-4a9e-bb38-ba771cc1cbd0">
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a0f79a1a-2dd3-410c-bdde-452a0f8c9c46)

Run ansible-hw-playbook.yml file
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/e7502d8e-7abf-4fb0-b97c-775c844cd65d)
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/2557550e-851e-4ef5-accf-98254a3a55b4)

Connect to linux-node1 i.e. “ansible-linux-node1” and verify that index.html file is written in /var/www/html
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a0ab4ddc-f45f-4797-b57e-50ded432d027)

Connect to ubuntu-node1 i.e. “ansible-node1” and verify that index.html file is written in /var/www/html
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a73aef8d-0195-45e5-b497-4cde2b51104b)

Verify GIT is installed in both linux and ubuntu nodes:
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/8c53e5b4-d676-4d7e-bee9-9435f725447c)
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/390358c6-d5c5-4ec5-9521-8346ec8e6aa7)












