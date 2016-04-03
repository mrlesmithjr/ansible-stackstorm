Role Name
=========

Installs StackStorm Community Edition (https://stackstorm.com/)  
###### StackStorm is an event-driven automation platform that ties together every component of your environment.

Requirements
------------

Install Ansible required roles...  
````
sudo ansible-galaxy install -r requirements.yml
````

Role Variables
--------------

````
---
# defaults file for ansible-stackstorm
stackstorm_db_info:
  user: 'mistral'
  password: 'StackStorm'
  db: 'mistral'
stackstorm_debian_packages:
  - 'apache2-utils'
  - 'python-passlib'
  - 'st2'
  - 'st2mistral'
  - 'st2web'
stackstorm_debian_repo_info:
  repo_key: 'https://packagecloud.io/StackStorm/staging-stable/gpgkey'
  repos:
    - 'deb https://packagecloud.io/StackStorm/staging-stable/{{ ansible_distribution|lower }}/ {{ ansible_distribution_release|lower }} main'
    - 'deb-src https://packagecloud.io/StackStorm/staging-stable/{{ ansible_distribution|lower }}/ {{ ansible_distribution_release|lower }} main'
stackstorm_ssh_info:
  user: 'stanley'
stackstorm_ssl_info:
  cert_days: 3650
  cert_dir: '/etc/ssl/st2'
  cert_info: '/C=US/ST=California/L=Palo Alto/O=StackStorm/OU=Information Technology/CN={{ ansible_hostname }}'
stackstorm_webui_login_info:
  password: 'Ch@ngeMe'
  password_file: '/etc/st2/htpasswd'
  user: 'st2admin'
````

Dependencies
------------

Follow install instructions under requirements to install required  
Ansible roles below.  
````
ansible-mongodb
ansible-nginx
ansible-postgresql
ansible-rabbitmq
ansible-stackstorm
````

Example Playbook
----------------

````
- hosts: test-nodes
  become: true
  vars:
    - pri_domain_name: 'test.vagrant.local'
  roles:
    - role: ansible-mongodb
    - role: ansible-nginx
    - role: ansible-postgresql
    - role: ansible-rabbitmq
    - role: ansible-stackstorm
  tasks:
````

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
