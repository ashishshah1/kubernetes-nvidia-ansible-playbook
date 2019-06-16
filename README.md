# kubernetes-nvidia-ansible-playbook
Ansible playbook for the installation of nvidia drivers, nvidia docker and kubernetes with GPU support

This guide assumes you're usuing ubuntu 18.04. The playbook may need some editing if you're using other versions of ubuntu or linux

# Instructions for use

## Step 1 - Enable ssh login between the client (your pc / laptop) and the machines you wish to install the drivers + kubernetes on

In order for ansible to work you only need to enable ssh login via root using a key. You don't need to install ansible on any machine other than the one you're working on, which can be your personal computer outside your cluster.

1. First, on each of the machines in your cluster install and enable openssh (to allow you to ssh into the machines).

~~~~
sudo apt-get update
sudo apt-get install openssh-server
~~~~

2. Second, allow the ability to ssh into the machines as root

On each machine input:
~~~~
sudo passwd
~~~~

Expected output:
~~~~
[sudo] password for linuxconfig: 
Enter new UNIX password: 
Retype new UNIX password: 
passwd: password updated successfully
~~~~

