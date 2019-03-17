# docker-linux-ansible
Install docker  on Linux flavors using ansible

### Prepare inventory file
A sample inventory file has been provided in [Ansible playbook directory](ansible/inventory/docker.ini).

your inventory should be defined as:

```
[node-linux]
#xxserverIPxx windows_node_hostname=xxxxx

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
### Run mssql container
```
ansible-playbook -i inventory/docker.ini run-mssql-linux.yml
```

That's  it :)
