# Archivematica Ansible Deploy #

Non-Official Archivematica Deployment through Ansible

This code is currently tested against CentOS 7 and Ubuntu 18.04 with Ansible 2.9.5

### Single node deployment ###
In the folder single_deploy you find the configuration to deploy all services used by Archivematica to a single node.
Change the configuration in group_vars/all.yml, rename host_vars/singlenode.example.com.yml file to your server name and make this change also in the hosts file.

### Multi node deployment ###
In the folder multi_deploy you find the configuration to deploy services used by Archivematica onto the servers you prefer.
Change the configuration in group_vars/all.yml, rename all files in host_vars to your server cluster and make this change also in the hosts file.

### Usage ###
After changing the configuration in all.yml and specified the servers in hosts and host_vars run these commands to start deploying:
Please run pre-playbook-ubuntu.yml first when Python 2.7 is not installed on destination servers.

1. ansible-galaxy install -r requirements.yml -p ./roles/
2. ansible-playbook -i hosts pre-playbook-ubuntu.yml
3. ansible-playbook -i hosts playbook.yml

### Python 2.x ###
Currently all Ansible code and Archivematica depends on Python 2.x. Please make sure that this Python version is installed before running the playbook. Python 3.x support is in development

### Support ###
This is still work in progress, let me know if there are any improvements available.
