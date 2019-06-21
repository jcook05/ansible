# ansible

playbook: local-ubuntu

## Caution, running this playbook will make changes to your system.   Please read the /tasks/system.yml and the vars file prior to running.  

Ansible Playbook that will configure a local WSL Ubuntu 18.04.1 LTS with Docker CE and allow it to be linked to Docker For Windows


For additonal information on Ansible setup please see the Ansible startup guide here:   http://docs.ansible.com/ansible/latest/intro_getting_started.html


To Use:

1. update your /etc/ansible/hosts file with the below entry

localhost ansible_connection=local

2.  Set Docker For Windows Settings/General to expose Daemon on localhost:2375 without TLS
  
3.  Run the playbook.  Here is an aws example:   ansible-playbook local-ubuntu.yml  --become --verbose

4.  Verify docker and docker-compose were installed:   run:  docker info  and docker-compose --version  

5.  Link your WSL docker to your Docker For Windows:  echo "export DOCKER_HOST=tcp://localhost:2375" >> ~/.bashrc && source ~/.bashrc
                              



