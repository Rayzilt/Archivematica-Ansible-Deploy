# Archivematica Ansible Deploy #

Non-Official Archivematica Deployment through Ansible

This code is currently only tested against CentOS 7 with Ansible 2.9.4
This would probably run on Ubuntu if the firewalld role is disabled in the playbook.

### Single node deployment ###
In the folder single_deploy you find the configuration to deploy all services used by Archivematica to a single node.
Change the configuration in group_vars/all.yml, rename host_vars/singlenode.example.com.yml file to your server name and make this change also in the hosts file.

### Multi node deployment ###
In the folder multi_deploy you find the configuration to deploy services used by Archivematica onto the servers you prefer.
Change the configuration in group_vars/all.yml, rename all files in host_vars to your server cluster and make this change also in the hosts file.

### Usage ###
After changing the configuration in all.yml and specified the servers in hosts and host_vars run these commands to start deploying:

1. ansible-galaxy install -r requirements.yml -p ./roles/
2. ansible-playbook -i hosts playbook.yml

### Support ###
This is still work in progress, let me know if there are any improvements available.
