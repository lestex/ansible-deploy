**Deploy rails application with ansible and capistrano**
========================================================

Setup Ansible on Mac:
> brew install ansible

Setup Ansible on Ubuntu:

> sudo apt-get install software-properties-common sudo
> sudo apt-add-repository ppa:ansible/ansible 
> sudo apt-get update sudo
> sudo apt-get install ansible

Check ansible version: 
> ansible --version

Clone this repo:
> git clone https://github.com/lestex/ansible-deploy.git

Put some config variables in playbook.yml: 

 - YOU_NAME - github account name
 - YOU_NAME_APP - app name
 - YOU_IP_SERVER - your VM's ip address

Run playbook:

> ansible-playbook -iYOU_IP_SERVER, playbook.yml

This playbook will:
- Install nginx, postgresql, git and so on(check the source of playbook.yml)
- Copy ssh keys to user's .ssh directory
- Install rbenv, ruby and dependencies
- Create application directory in /home/user
- Setup database auth
- Copy nginx configs to /etc/nginx/nginx.conf (optionaly: to /home/user and create symlink)