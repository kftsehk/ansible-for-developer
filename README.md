# Ansible for HPC

This repository uses ansible and various roles to config CentOS 7 workstation with GPU for quite general purpose:
- Deep Learning
- Scientific computing
- Web and AWS cloud development

# Other installs

https://developer.nvidia.com/blog/streamlining-nvidia-driver-deployment-on-rhel-8-with-modularity-streams/

# Usage

From a fresh copy of RHEL 8

```
# Install prerequisite
sudo subscription-manager repos --enable ansible-2-for-rhel-8-x86_64-rpms
sudo dnf -y install ansible

# git clone this repository
git clone https://github.com/kftsehk/ansible-for-hpc.git

# fetch some additional roles from galaxy
ansible-galaxy install -r requirements.yml

# Make necessary change to workstation.yml if you wish to change some installed packages or variables
# This final command starts the main ansible playbook to setup a workstation
# If installed from local and require a reboot to install GPU driver, reboot and run again
ansible-playbook -K workstation.yml
```
