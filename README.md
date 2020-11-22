# WORK IN PROGRESS 

# Ansible Playbooks : Canaima

Ansible Playbooks for Canaima project.

Please find the complete project's documentation [here](https://github.com/canaima-project)

## Getting Started

### Presentation

#### install.yml

## Prerequisites

#### Network


## Installing Canaima
#### SSH
```
apt-get install ansible git -y
git clone git@github.com:toreatessier/canaima.git
cd ansible/ansible-canaima
ansible-galaxy install -r roles/requirements.yml -p roles
ansible-playbook install.yml
```

#### HTTPS
```
apt-get install ansible git -y
git clone https://github.com/toreatessier/canaima.git
cd ansible/ansible-canaima
ansible-galaxy install -r roles/requirements.yml -p roles
ansible-playbook install.yml
```

### Deploying Canaima's services

## Notes

The playbook runs locally. 
Modify eventually inventory.ini to set your list.
Deploy ssh authorized keys for remote execution.

## Authors

* **Toréa TESSIER** - <torea.tessier2@gmail.com> - [Canaima Project](https://github.com/canaima-project/)
