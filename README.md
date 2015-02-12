devstack
=========

Run openstack on a single instance via [devstack](http://docs.openstack.org/developer/devstack/). Once installed the web ui should be accessable via http://yourinstalledurl.com/

Requirements
------------
```
# file /requirements.yml
- src: chrismeyersfsu.devstack
```
`ansible-galaxy install -r requirements.yml` to install this role.

Tested on Ubuntu 14.04. Only supports apt package manager.

Role Variables
--------------

`nova_password` SHOULD be overridden.

`nova_groups` describes the instances to spin up on the devstack instance. This is helpful for exploring a populated API.
```
nova_groups:
  - group_name: eastcoast
    instance_name: deceptacon
    instance_count: 3
  - group_name: westcoast
    instance_name: autobot
    instance_count: 2
```

Dependencies
------------
None


Example Playbook
----------------

The simpliest usage of the devstack role will setup devstack and instantiate 5 vm instances.
```
hosts: all
roles:
  - chrismeyersfsu.devstack
```

For more complex and featurful uses of the role please see (playbook-devstack)[https://github.com/chrismeyersfsu/playbook-devstack]

License
-------

GPLv2

Author Information
------------------

Chris Meyers. This is his first playbook.
chris.meyers.fsu@gmail.com