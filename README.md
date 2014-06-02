Summary
=======

Testing out some simple commands from DevOpsU Taste Test book using Vagrant

Starting and Provisioning
=========================

Bring the VMs up:

```shell
$ vagrant up
```

Provision via Vagrant:

```shell
$ vagrant provision
```

Or, via Ansible commands:

```shell
$ ansible-playbook -i provision/inventory.ini provision/site.yml
```

Note: See `ansible.cfg` for settings that allow direct Ansible commands (on my MacBook at least)

Viewing
=======

Go to:

* [web1](http://localhost:8080)
* [web2](http://localhost:8080)
