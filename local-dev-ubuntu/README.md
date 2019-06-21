# ansible

playbook: local-ubuntu

## Caution, running this playbook will make changes to your system.   Please read the /tasks/system.yml and the vars file prior to running.  

Ansible Playbook that will configure a local Ubuntu 18.04.1 LTS with some standard cloud development tools such as Node.js, Terraform, Packer, Python and the AWS CLI.  It can be used for Windows WSL with 0 issues. 


For additonal information on Ansible setup please see the Ansible startup guide here:   http://docs.ansible.com/ansible/latest/intro_getting_started.html


To Use:

1. update your /etc/ansible/hosts file with the below entry

localhost ansible_connection=local
  
2.  Run the playbook.  Here is an aws example:   ansible-playbook local-ubuntu.yml  --become --verbose
                              



