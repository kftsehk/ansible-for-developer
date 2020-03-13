# Ansible for HPC

This repository is currently mainly for configuring workstation with GPU using CentOS 7 (tested on CentOS 7.7).

# Usage

From a fresh copy of CentOS (minimal or other)

```
# [sudo required]
sudo yum -y install git ansible

# git clone this repository
git clone https://github.com/kftsehk/ansible-for-hpc.git

# [sudo required] run twice in case updating jinja 2.8 fail at the first time
ansible-playbook -K bootstrap-ansible-control-centos7.yml
ansible-playbook -K bootstrap-ansible-control-centos7.yml

# fetch some additional roles from galaxy
ansible-galaxy install -r requirements.yml

# Make necessary change to workstation.yml if you wish to change some installed packages or variables
# [sudo required] This final command starts the main ansible playbook to setup a workstation
ansible-playbook -K bootstrap-ansible-control-centos7.yml
```