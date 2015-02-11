devstack
=========

Run openstack on a single instance via [devstack](http://docs.openstack.org/developer/devstack/). Once installed the web ui should be accessable via http://yourinstalledurl.com/

Requirements
------------

Tested on Ubuntu 14.04. Only supports apt package manager.

Role Variables
--------------
`nova_auth_url` must be set appropriately
```
nova_auth_url: "http://devstack.testing.ansible.com:5000/v2.0/"
```


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



Example Playbook
----------------

The simpliest usage of the devstack role will setup devstack and instantiate 5 vm instances.
```
    - { role: devstack, nova_setup: true, nova_groups: undefined, tags: devstack_setup }
```

To JUST install devstack.
```
    - { role: devstack, nova_setup: true, nova_groups: undefined, tags: devstack_setup }
```

To JUST invoke the 5 vm creations.
```
    - { role: devstack, nova_setup: false, tags: devstack_nova }
```

License
-------

BSD

Author Information
------------------

Chris Meyers works for Ansible. This is his first playbook.
