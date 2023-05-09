# COMMANDS

- THIS MAKES SURE THAT ANSIBLE CAN CONNECT TO THE SERVERS IN THE INVENTORY FILE:
'ansible all --key-file ~/.ssh/ansible -i inventory -m ping'

- can be shortened to:
'ansible all -m ping' (because we declared the default inventory file in ansible.cfg)

- this lists all the hosts in the inventory file:
'ansible all --list-hosts'

- using a module (the -m flag) to run a command on all hosts:
'ansible all -m gather_facts' (this shows the facts of all hosts)

- to be ROOT USER:
'ansible all -m apt -a "name=nginx state=latest" --become --ask-become-pass' (this installs nginx on all hosts, but first asks you the password to become root)
