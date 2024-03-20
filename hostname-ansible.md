# hostname
==============================
hostname
# or #
hostnamectl
# another option #
cat /etc/hostname

sudo hostnamectl set-hostname stats1.opensourceflare.com
sudo reboot



# ansible-installation:
=================================================
amazon-linux-extras list | grep ansible

sudo amazon-linux-extras install ansible2 -y

ansible — version

sudo nano /etc/ansible/hosts



-----------------------------------------------------------------------------------
# Install Ansible:
-------------------

sudo yum install epel-release

sudo yum install python-pip

yum install ansible 

# Create SSH Connection:
------------------------

ssh-keygen

Press enter for all questions. The public and private key will be created in the location : /root/.ssh/id_rsa

Run the below command to copy the key to other machines. 

ssh-copy-id user@ip 

eg: ssh-copy-id root@192.168.239.111

# Ansible Modules:
-------------------------

## Ping Module:
ansible testservers -m ping

## File module: Creating and deleting directory

```
ansible testservers -m file -a "dest=/root/file state=directory"
```

ansible testservers -m file -a "dest=/root/file mode=755 owner=root group=root state=directory"

ansible testservers -m file -a "dest=/root/file state=absent"

## Copy Module:

ansible testservers -m copy -a "src=/root/file/text.txt dest=/root/"

## Shell Module:

ansible testservers -m shell -a "mkdir test"

## Yum Module:

ansible testservers -m yum -a "name=wget state=present"
ansible testservers -m yum -a "name=httpd state=present"


## Service Module:

ansible testservers -m service -a "name=httpd state=restarted"
ansible testservers -m service -a "name=httpd state=started"
ansible testservers -m service -a "name=httpd state=stopped"

## restarting the servers:

ansible testservers -a "/sbin/reboot"






## Ansible Master and node connection establishing commands
=======================================================================================
 
    1 clear
    
    2  sudo hostnamectl set-name master-ansible
    
    3  sudo hostnamectl set-hostname master-ansible
    
    4  sudo sysyemstl reboot
    
    5  sudo systemctl reboot
    
    7  clear
    
    8  sudo apt update
    
    9  sudo apt install ansible
    
    10  ansible --version
   
    11  ssh-keygen
   
    12  sudo /etc/ansible/
   
    13  sudo cd /etc/ansible/
   
    14  cd /etc/ansible/
   
    15  ls
   
    16  sudo vi hosts
   
    17  cd
   
    18  sudo vi /etc/ssh/sshd_config
   
    19  sudo systemctl sshd restart
   
    20  sudo systemctl restart sshd

## Change password authentication to yes in node sever also

   18  sudo vi /etc/ssh/sshd_config
   
   19  sudo systemctl sshd restart
   
   20  sudo systemctl restart sshd



   ## Copying public key to node server
    2 sudo hostnamectl set-name master-ansible
    
    3  sudo hostnamectl set-hostname master-ansible
    
    4  sudo sysyemstl reboot
    
    5  sudo systemctl reboot
    
    6  CLEAR
    
    7  clear
    
     8  cd
     
    9  sudo ssh-copy-id ubuntu@172.31.94.237
    
   10   ls
   
   11  cd .ssh/
   
   12  ls
   
   13  sudo ssh-copy-id ubuntu@172.31.94.237
   
   14  sudo ssh-copy-id root@172.31.94.237
   
   15  ssh-copy-id -i root@172.31.94.237
   
   16  clear
   
   17  ssh-copy-id -i ubuntu@172.31.94.237
   
   18  ansible all -m ping


