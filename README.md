# Ansible for HPC

This repository uses ansible and various roles to config CentOS 7 workstation with GPU for quite general purpose:
- Deep Learning
- Scientific computing
- Web and AWS cloud development

# Usage

From a fresh copy of CentOS (minimal or other)

```
# Install prerequisite
sudo yum -y install centos-release-ansible-29
sudo yum -y install git ansible

# git clone this repository
git clone https://github.com/kftsehk/ansible-for-hpc.git

# run twice in case updating jinja 2.8 fail at the first time
ansible-playbook -K bootstrap-ansible-control-centos7.yml
ansible-playbook -K bootstrap-ansible-control-centos7.yml

# fetch some additional roles from galaxy
ansible-galaxy install -r requirements.yml

# Make necessary change to workstation.yml if you wish to change some installed packages or variables
# This final command starts the main ansible playbook to setup a workstation
# If installed from local and require a reboot to install GPU driver, reboot and run again
ansible-playbook -K bootstrap-ansible-control-centos7.yml
ansible-playbook -K bootstrap-ansible-control-centos7.yml
```
