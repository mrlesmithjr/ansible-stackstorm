Role Name
=========

An [Ansible] role to install/configure [StackStorm] Community Edition

[StackStorm] is an event-driven automation platform that ties
together every component of your environment.

Requirements
------------

Install [Ansible] [required](./requirements.yml) roles...  
```
sudo ansible-galaxy install -r requirements.yml
```

Role Variables
--------------

[Role Defaults](defaults/main.yml)

Dependencies
------------

None

Example Playbook
----------------

[Example Playbook](./playbook.yml)

[Vagrant]
-------
Spin up [StackStorm] using [Vagrant].
```
cd Vagrant
vagrant up
```
You should now be able to connect to https://192.168.250.10

Login using: `st2admin\Ch@ngeMe`

When you are all done testing using [Vagrant] you can easily tear down and
cleanup:
```
./cleanup.sh
```

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[Ansible]: <https://www.ansible.com>
[StackStorm]: <https://stackstorm.com/>
[Vagrant]: <https://www.vagrantup.com/>
