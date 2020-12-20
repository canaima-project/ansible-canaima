# Ansible Playbooks : Canaima

Ansible Playbooks for Canaima project.

Please find the complete project's documentation [here](https://github.com/canaima-project)

## Getting Started

### Presentation

This repo is made to be the **only one** to be cloned to deploy Canaima project's services.
It automatically clones Canaima's different ansible roles :
- *[VM_creation]*(https://github.com/canaima-project/ansible-role-vm_creation) : automated CentOS / Debian VM creation **and** configuration
- *[Mesos]*(https://github.com/canaima-project/ansible-role-mesos) : Mesos orchestration service deployment
- *[Hadoop]*(https://github.com/canaima-project/ansible-role-mesos) : Hadoop service deployment
- *[Spark]*(https://github.com/canaima-project/ansible-role-mesos) : Spark service deployment
- *[ELS]*(https://github.com/canaima-project/ansible-role-mesos) : ElasticSearch service deployment

#### install.yml

This playbook will deploy Canaima in the production environnement which is composed by the following compute ressources (Cauchy) :
- canaima_pc1 192.168.4.7
- canaima_pc2 192.168.4.152 
- canaima_pc3 192.168.4.92 
- canaima_pc4 192.168.4.86
- canaima_pc5 192.168.4.137
- canaima_pc6 192.168.4.214

It is made to deploy :

- **Mesos masters** (3 nodes + zookeeper - no need to boostrap the cluster)
- **Hadoop cluster** (3 nodes, deploys HDFS + applicative layer)
- **Spark cluster** (3 nodes)
- **ElasticSearch**

## Prerequisites

#### Network
- Cisco Catalyst 2960 (switch) with minimal install and SSH enabled
- Cisco 2911 (router) with minimal install and SSH enabled
- OK for Cauchy room

## Installing Canaima
### SSH
```
apt-get install ansible git -y
git clone git@github.com:toreatessier/canaima.git
cd ansible/ansible-canaima
ansible-galaxy install -r roles/requirements.yml -p roles
ansible-playbook install.yml
```

### HTTPS
```
apt-get install ansible git -y
git clone https://github.com/toreatessier/canaima.git
cd ansible/ansible-canaima
ansible-galaxy install -r roles/requirements.yml -p roles
ansible-playbook install.yml
```

**Important** : Depending on the service you want to deploy, *inventory.ini* file **has** to be changed. Please make sure IPs variables are set.

## Notes

The playbook runs locally. 
Modify eventually inventory.ini to set your list.
Deploy ssh authorized keys for remote execution.

## Authors

* **Toréa TESSIER** - <torea.tessier2@gmail.com> - [Canaima Project](https://github.com/canaima-project/)
