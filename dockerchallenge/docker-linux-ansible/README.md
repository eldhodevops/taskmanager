# docker-linux-ansible
Install docker  on Linux flavors using ansible

#I used Ubuntu 18.04 with oracle virtual box

```
cat /etc/os-release 
NAME="Ubuntu"
VERSION="18.04.1 LTS (Bionic Beaver)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 18.04.1 LTS"
VERSION_ID="18.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=bionic
UBUNTU_CODENAME=bionic

```

#### Prepare Ansible Host system
- Setup for ansible host  on Ubuntu system ( It can be use your Laptop , do not use Servers)
```
apt-get update
apt-get -y install software-properties-common
apt-add-repository -y ppa:ansible/ansible
apt-get update
apt-get install -y ansible python-pip
```
### Prepare inventory file
A sample inventory file has been provided in [Ansible playbook directory](ansible/inventory/docker.ini).

your inventory should be defined as:

```
[node-linux]
127.0.0.1 ansible_connection=local ansible_python_interpreter=/usr/bin/python3

```
### Prepare authentication to Node

 All the sample files has been provided in [Ansible playbook group_var directory](ansible/group_vars).
you need to edit with example below

- Edit username and password inside the file group_vars/node-linux.yml
```
ansible_user: xxusernamexx
# Ensure you don't have ansible_ssh_pass var set in your own group_vars/all.yml, it will overwrite this.
ansible_password: xxpasswordxx
ansible_port: portxx
```
### Run playbook
```
ansible-playbook -i inventory/docker.ini install-docker.yml
```

That's  it :)
