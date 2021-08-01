# Rolling SSH-KEY
[![Builds](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

---
# Description

Assume that certain situations occur that your existing ssh-key has compromised and need to pay attention. Here comes the advantage of using Ansible ssh-key rolling. You can use this Ansible-playbook to revoke the existing ssh-keys that's being used up by the instances and to create new keys in a hassle free manner. Moreover, this could be implemented for  security hardening your ssh-key by updating it monthly.

---

# Features

- Ansible-Dynamic inventory is ued to collect the details of instances that use the existing key-pair.
- Easy implementation and hassle free ssh-key rotation.

---
# Prerequisites

- Need to have Ansible installed in your machine.
- Need to have Boto3 installed in your machine.
- IAM role with attached policies for accesing ec2.
- Need to copy the existing ssh-private-key file to the directory that you are planning to execute the ansible-playbook.

---
# Installation 

- [Ansible installation](https://docs.ansible.com/ansible/latest/index.html) 
- [Boto3 Installation](https://pypi.org/project/boto3)
---
# How to clone this repository and execute in Ansible master.
_Steps:_
```sh
mkdir ansible
cd ansible
yum install pip git -y
pip install ansible
pip install boto
pip install boto3
git clone https://github.com/amalbosemathew/ansible_ssh_key_rolling
cd ansible_ssh_key_rolling/
ansible-playbook main.yml --syntax-check
ansible-playbook main.yml

```

### Screenshots

Rotating the SSH-KEY :

![alt text](https://i.ibb.co/3BPhQZ0/1.png)


# Conclusion

The intention of this project is to enhance a rolling update of existing ssh key. The playbook will fetch the list of instances in the particular region  mentioned in the "aws.vars" file and update the old ssh-keys with new one in each instances at a glance and upload the same to AWS.


