Role Name
=========

This role will deploy Quay (https://www.projectquay.io).

Supported deployments are:

Basic Deploy (Single Machine)
High Availability (Cluster - 3 Quay + 1 DB node)


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
