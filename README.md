# ANSIBLE-Project-on-AWS
This repo contain all ansible playbook project for AWS

# Ansible Playbook Project1
## Setup an Ansible cluster with the controller running on Amazon Linux 2 and the 4 nodes in which 2 running on Amazon linux and 2 running on ubuntu.

![Alt text](images/achitecture-Ansible-ubuntu-controller.png)

### Write a playbook with four (4) plays:
* Play1: Deploy apache on ubuntu clients
* Play2: Deploy apache on amazon clients
* Play3: Deploy git on amazon linux clients
* Play4: Deploy git on ubuntu clients

# STEPS BY STEPS PROCESS 

### 1. Launched 3 amazon linux and 2 ubuntu server:
![Alt text](images/ec2-intance.png)


### 2. Installed ansible on linux-ansible-controller:
- Take up you privilage. the first command for ubuntu and the second for linux. 
```
sudo su - ubuntu
```
```
sudo su - ec2-user
```
- let rename our ubuntu server to "ansible-controller"
```
sudo hostname ansible-controller
```
- For the command to take effect you need to exit(with the command bellow) and login again(with the fist command above)
```
exit
```
- let verifie if python3 and ansible is install 
```
 python3 --version
```
```
 ansible --version
```
- After the verification we notice ansible is not install. So we need to go to the officail documentation [this page](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html) depending on our OS we follow the steps and install. For us is Installing Ansible on Ubuntu 
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```
![Alt text](images/ansible-install.png)

### 3. Establish SSH connection between Ansible master(controller) and clients(nodes)
#### To do this we need to first generate ssh key pair "id_rsa.pub public key"

- First is to connect as a sudo (the root user) with the command below 
```
 sudo -i
```
- Then we generate our key as a root user
```
 ssh-keygen -t rsa
```
- Let go to the location where the keys have been created
```
 cd .ssh
```
```
 ls -l
```

- Now, let cat into the pub key and copie. This pub key will be use for our nodes
```
 cat id_rsa.pub
```
![Alt text](images/key-generate.png)


- We notice that our cfn-lint is not install so we use the command copie from our officail git repo of cfn-lint shown above
- We notice that our cfn-lint is not install so we use the command copie from our officail git repo of cfn-lint shown above


![Alt text](images/buildstage1.png)
![Alt text](images/buildstage2.png)




### 3. Verified ansible is installed in linux-ansible-controller. And generated ssh key-pair. Copied the public key to all 4 nodes:

<img width="512" alt="image" src="https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/088d1bbd-a60b-441e-9b36-99c90b0a2390">


### 4. Updated “hosts” file in ansible-controller.

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/ae396a32-ee5a-4d9a-af68-18d0a6fb98ff)


### 5. Test the connectivity in-between the controller and nodes:

<img width="590" alt="image" src="https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/dffc2ab1-b43b-4a9e-bb38-ba771cc1cbd0">

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a0f79a1a-2dd3-410c-bdde-452a0f8c9c46)


### 6. Run ansible-hw-playbook.yml file

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/e7502d8e-7abf-4fb0-b97c-775c844cd65d)

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/2557550e-851e-4ef5-accf-98254a3a55b4)


### 7. Connect to linux-node1 i.e. “ansible-linux-node1” and verify that index.html file is written in /var/www/html

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a0ab4ddc-f45f-4797-b57e-50ded432d027)


### 8. Connect to ubuntu-node1 i.e. “ansible-node1” and verify that index.html file is written in /var/www/html

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/a73aef8d-0195-45e5-b497-4cde2b51104b)


### 9. Verify GIT is installed in both linux and ubuntu nodes:
![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/8c53e5b4-d676-4d7e-bee9-9435f725447c)

![image](https://github.com/Fokoue22/ANSIBLE-Project-on-AWS/assets/117523566/390358c6-d5c5-4ec5-9521-8346ec8e6aa7)





## Author
FOKOUE THOMAS






