[![Build Status](https://travis-ci.org/twling/ansible-role-quay.svg?branch=master)](https://travis-ci.org/twling/ansible-role-quay)

Role Name
=========

This role will deploy Quay (https://www.projectquay.io).

Supported deployments are:

* Basic Deploy (Single Machine)
* High Availability (Cluster - 3 Quay + 1 DB node)


Requirements
------------

The following requirements are outside the scope of this role and require proper configuration
and deployment before this role can be executed.

Basic Deploy requirements(Additional details: https://docs.projectquay.io/deploy_quay.html) :

* RHEL based server pre-configured with proper repositories/subscriptions


High Availability requirements(Additional details: https://docs.projectquay.io/deploy_quay_ha.html):

* All Basic Deploy requirements, for 3 quay nodes and a database node
* Object Storage (S3/Swift/etc)
* Loadbalancer (haproxy/ngninx/etc)

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

N/A

Testing
------------

This role is developed using the Molecule testing framwork, using the vagrant+lib plugin. Using Docker for testing is avoided
here as the Quay service runs on as a container and Docker-in-Docker can be problemeatic.

Testing Setup:

*Fedora 32*

```
sudo dnf install -y libvirt vagrant vagrant-libvirt vagrant-sshfs python3-pip python3-devel python3-libselinux
python3 -m pip install --user molecule[lint] molecule-vagrant pytest-flake8
```

Executing Tests:

```
molecule test
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      tasks:
         
        - name: "Include Quay Role"
          include_role: "quay" 

License
-------

GPL v3.0

Author Information
------------------

Timothy Ling <tling@redhat.com>
