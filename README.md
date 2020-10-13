# Ansible-Playbook - Cisco IOS Upgrade Tool

A simple ansible playbook to check if your IOS exists in flash, if not, FTP your IOS, verify MD5 and set this to Boot.

# Use Case Description
This playbook will help to upgrade multiple Cisco IOS's quickly.

# Installation
Requires Python, Ansible and Ansible Galaxy IOS
Centos:
yum install python
yum install ansible
ansible-galaxy collection install cisco.ios

# Configuration
Edit the hosts files to add your invetory of switches, I recommended starting with a single test router
Edit the file under Group-vars to setup your individual variables, eg, IOS, FTP, MD5 value and Username and Password

# How to Test
Run this on a few test routers first, do not just begin using in Production.

To launch ansible Playbook: ansible-playbook -i hosts update_ios.yml


# Credits and References:
More Galaxy IOS Modules
https://galaxy.ansible.com/cisco/ios?extIdCarryOver=true&sc_cid=701f2000001OH6uAAG

Training:
Hands-on Ansible Video Course by Sander van Vugt

Cisco Devnet:
https://developer.cisco.com/devnetcreate/2020/
