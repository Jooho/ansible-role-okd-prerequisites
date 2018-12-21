Ansible Role: OKD pre-requisites processes
=========

This role help config pre-requisites process for OKD installation

*Details*
- Install required packages
- docker setup(install/storage-overlay2)
- intrim dns config


Requirements
------------
None

Role Variables
--------------

| Name                | Default value | Requird | Description                                                 |
| ------------------- | ------------- | ------- | ----------------------------------------------------------- |
| node_type           | undefined     | yes      | OKD host type(okd-host or okd-lb)                          |
| okd_version         | 3.11          | no      | OKD version                                                 |
| docker_version      | 1.13.1        | no      | Docker version                                              |
| docker_storage_disk | vdb           | no      | Disk name for docker storage(ex, vdc)                       |
| interim_dns_use     | false         | no      | Set true, if you set interim dns                            |
| interim_dns_ip      | undefined     | yes     | If you set true to interim_dns_use, you must set this value |


Dependencies
------------

None



Example Playbook
----------------
~~~
- name: Example Playbook
  hosts: localhost
  tasks:
    - import_role:
        name: ansible-role-okd-prerequisites
      vars:
        node_type: okd-host
        interim_dns_use: true
        interim_dns_ip: 10.10.10.1
~~~

License
-------

BSD/MIT

Author Information
------------------

This role was created in 2018 by [Jooho Lee](http://github.com/jooho).
