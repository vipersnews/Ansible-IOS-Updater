# Ansible - Cisco IOS Upgrade Tool

A simple ansible script to check if your IOS exists in flash, if not, FTP your IOS, verify MD5 and set this to Boot.

This uses an inventory for all your hosts, a group-vars file for your username and password.

To Run: ansible-playbook -i hosts update_ios.yml
