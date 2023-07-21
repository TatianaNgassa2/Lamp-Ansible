# LAMP on Ubuntu 18.04

1- install ansible on your machine

  only step 1 of  https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-22-04

2- install ssh 
   https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/

3- create ssh keys on your machine with this command: ssh-keygen
   

4- create a virtual machine 
  https://www.tecmint.com/install-qemu-kvm-ubuntu-create-virtual-machines/


5- copy public ssh key to your virtual machine

6- put virtual machine ip address in /etc/ansible/host

  example: 
       [servers]
       server1 ansible_host=virtual_machine_ip_address ansible_user=virtual_machine_user

7-  in /etc/ansible/ansible.cfg put:
 
    [defaults]
    remote_user=virtual_machine_user

8- test ansible connection to your virtual machine

    ansible all -m ping -u ntt

9- Go to playbook.yml directory and run:

    ansible-playbook   playbook.yml --extra-vars "ansible_sudo_pass=virtual_machine_user_password"

