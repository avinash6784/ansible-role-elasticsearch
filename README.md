# Ansible Role: Elasticsearch
An Ansible Role that installs Elasticsearch on RedHat/CentOS

## Requirements

Requires Java (Preferred Java 8+). See [`avinash6784.oracle-java`](https://github.com/avinash6784/ansible-oracle-java) role to install Java 8.

## Role Variables
Available variables are listed below, along with default values (see `defaults/main.yml`):
```yml

# Elasticsearch major version
elsticsearch_major_version: 5.x

# Elasticsearch cluster name
elasticsearch_cluster_name: my_cluster

# Elasticsearch node name
elasticsearch_node_name: my_node

# Network host to listen for incoming connections on. By default we only listen on the localhost interface. Change this to the IP address to listen on a specific interface, or 0.0.0.0 to listen on all interfaces.
elasticsearch_network_host: localhost

#The port to listen for HTTP connections on.
elasticsearch_http_port: 9200

#Whether to allow inline scripting against ElasticSearch. 
elasticsearch_script_inline: true
elasticsearch_script_indexed: true
```

## Dependencies

This role depends on avinash6784.oracle-java role. This is configured for ansible-galaxy install in requirements.yml.

**NOTE**: Requirements are installed as virtual user avinash6784 (avinash6784.oracle-java).

Be sure to install required roles with
```
ansible-galaxy install --role-file requirements.yml
```

## Usage and Example Playbook

Install from Ansible Galaxy
```
$ ansible-galaxy install avinash6784.elasticsearch
```
Or download manually
```
$ git clone https://github.com/avinash6784/ansible-role-elasticsearch.git
```
The code should reside in the roles directory of ansible ( See ansible documentation for more information on roles ), in a folder ansible-role-elasticsearch.

## Run the playbook

First create a playbook including the git role, naming it test.yml.
```yml
- name: Install Elasticsearch
  hosts: localhost
  become: true
  roles:
    - ansible-role-elasticsearch

$ ansible-playbook -i hosts test.yml
```

## Author Informations

This role was created by [Avinash Pawar](http://devopstechie.com).

