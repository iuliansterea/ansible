# ansible
Install Ansible on CentOS

yum update -y <br>
yum install epel-release -y <br>
yum install ansible -y <br>


# How to Install Pip on CentOS 
https://linuxize.com/post/how-to-install-pip-on-centos-7/


# create pass vault 
openssl rand -base64 2048 > vault.pass
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass
With hashed password file you must specify the vault-password-file argument when running Ansible playbook and won’t be asked for the password:

ansible-playbook playbook.yml --vault-password-file vault.pass
Edit the pass.yml file and create the keys global constants
Create the variables ec2_access_key and ec2_secret_key and set the values gathered after user creation (IAM).

ansible-vault edit group_vars/all/pass.yml 
Vault password:
ec2_access_key: AAAAAAAAAAAAAABBBBBBBBBBBB                                      
ec2_secret_key: afjdfadgf$fgajk5ragesfjgjsfdbtirhf
