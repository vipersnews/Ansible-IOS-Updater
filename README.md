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

# How to Use
Run this on a few test routers first, do not just begin using in Production, this is what each play is designed to do:

      - name: CHECK IF {{ IOS }} ALREADY INSTALLED
This is checking flash for all bin files, you may need to adjust this to bootflash

      - name: Print if ios found
Show if the IOS was found or not, if it wasn't found, it will execute the below, if it was found, it will skip this step. 

      - name: UPGRADE IOS IMAGE IF NOT COMPLIANT
Upload from FTP (You could change this to SCP in the groupvars file)

    - name: VERIFY MD5
Verify MD5 against specified hash value in groupvars

    - name: SET BOOTVAR WHEN MD5 PASSES
 
If MD5 is valid, set IOS to boot

To launch ansible Playbook: ansible-playbook -i hosts update_ios.yml


# Credits and References:
I was inspired by the following to being my journey learning Ansible, this is my first script, I encourage you to learn more:
More Galaxy IOS Modules
https://galaxy.ansible.com/cisco/ios?extIdCarryOver=true&sc_cid=701f2000001OH6uAAG

Training:
Hands-on Ansible Video Course by Sander van Vugt

Cisco Devnet:
https://developer.cisco.com/devnetcreate/2020/
