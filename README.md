# Ansible Cloud Infrastructure

This repository contains a set of Ansible playbooks used for managing infrastructure across multiple Cloud Infrastructure providers.

## Supported Cloud Providers
* AWS
* Openstack

### Usage

#### AWS
##### Set Environment Variables
```
export AWS_ACCESS_KEY_ID='****'
export AWS_SECRET_ACCESS_KEY='****'
export AWS_REGION=us-east-1
```
##### Provision Infrastructure
```
ansible-playbook -i inventory/aws/ec2.py playbooks/provision.yml --extra-vars "cluster_name=<cluster-name> provider_type=aws"
```
##### Destroy Infrastructure
```
ansible-playbook -i inventory/aws/ec2.py playbooks/destroy.yml --extra-vars "cluster_name=<cluster-name> provider_type=aws"
```

#### Openstack
##### Set Environment Variables
```
export OS_AUTH_URL="https://example.com:13000/v2.0"
export OS_USERNAME="username"
export OS_PASSWORD="password"
export OS_TENANT_ID="****"
export OS_TENANT_NAME="tenant"
```
##### Provision Infrastructure
```
ansible-playbook playbooks/provision.yml --extra-vars "cluster_name=<cluster-name> provider_type=openstack"
```
##### Destroy Infrastructure
```
ansible-playbook playbooks/destroy.yml --extra-vars "cluster_name=<cluster-name> provider_type=openstack"
```
