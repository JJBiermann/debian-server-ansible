#  🤖 Linux Server managed with Ansible 

Hardens a Debian Server (tested on Debian 12 - Bookworm) with some minimal requirements from [How to secure a Linux Server](https://github.com/imthenachoman/How-To-Secure-A-Linux-Server).

Many roles are adapted from [How to secure a Linux Server with Ansible](https://github.com/moltenbit/How-To-Secure-A-Linux-Server-With-Ansible). If you want to get inspired for further hardening roles with ansible, have a look! 💖

`docker-playbook.yml` uses the docker role provided by [geerlingguy](https://github.com/geerlingguy/ansible-role-docker). 

## Running the Playbooks

In my case, I connect to a user which will get its privileges escalated by ansible, thus passing the `--ask-become-pass` is necessary. However, if you directly connect to root or a user which does not need a password to escalate to root priviliges, the `--ask-become-pass` can be ommitted. 

```console
ansible-playbook -i hosts --ask-become-pass -e ansible_ssh_private_key_file=</absolute/path/to/private/ssh-key> main-playbook.yml
```

## Prerequisites
The playbooks expect a minimal server setup with ssh preinstalled and a user already set up. 
SSH RootLogin does not have to be enabled! 

## NOTE
Depending on your needs for security, this setup might not be enough, or things might be missing. USAGE ON OWN RISK! 
