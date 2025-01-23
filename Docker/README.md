# Using Docker with Ansible

## Build a Docker container

From this cloned directory, run the Docker build command:

```
docker build -t my/ansible .
```

The trailing dot on the end is __*required*__.  You can change the name "my/ansible" to whatever you wish.  This will build a
container based on Python 3.11 and Ansible 2.18, and include the Check Point
Management API and Gaia API module collections.

```
$ docker run --name Ansible -t --rm -v ~/Documents/ansible:/home/ansible -w /home/ansible my/ansible ansible --version
ansible [core 2.18.1]
  config file = /home/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/lib/python3.11/site-packages/ansible
  ansible collection location = /root/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/local/bin/ansible
  python version = 3.11.11 (main, Jan 15 2025, 00:10:22) [GCC 12.2.0] (/usr/local/bin/python3.11)
  jinja version = 3.1.5
  libyaml = True
```
