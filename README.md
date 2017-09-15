# ansible

playbook: jenkins-ubuntu-fresh

Ansible Playbook that will spin up a Jenkins instance behind Nginx on Ubuntu 16.04.    This is a robust playbook that installs many of the tools necessary to support development
in a variety of languages.   This includes .Net Core 2.0, Java 1.8, Docker, Maven etc. 


These instructions assume that your Ansible Host is already configured to manage servers in your target environment.   Your ssh keys should be added and ready to go. 

For additonal information on Ansible setup please see the Ansible startup guide here:   http://docs.ansible.com/ansible/latest/intro_getting_started.html

To Use:

1. update your /etc/ansible/hosts file with the below entry
   [jenkinsfresh]
   <your ubuntu instance ip>

2. Ansible requires that Python be installed on the target instance.   If you are using a fresh AWS Ubuntu instance then include the user-data.sh script in the user-data as a file on instance launch or manually install python your instance

3.  Run the playbook.  Here is an aws example:   ansible-playbook jenkins-ubuntu.yml --user ubuntu --become --verbose
                              vagrant example:   ansible-playbook jenkins-ubuntu.yml --user vagrant --become --verbose

4.  When finished, navigate to <your ubuntu instance ip> in your browser and you should see the Unlock Jenkins page.   Follow the instructions to configure Jenkins. 

5.  Once Jenkins is configured, it is recommended that you test out the software installed as well as Jenkins.   You can do both by simply creating a Jenkins job and inserting a shell step with the following to test docker, dotnet and java installs
    dotnet --version
    docker --version
    java -version




