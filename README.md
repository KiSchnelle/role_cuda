Ansible Role for Installing Cuda on CentOS 7,8 and Ubuntu 20
=========

This will download and install cuda toolkit to the specified folders. If specified it also creates a modulefile in lua or tcl.
For compatible versions please check the defaults/main.yml

Requirements
------------

Working internet connection for download of the cuda runfile.

Role Variables
--------------

Variables can be changed in defaults/main.yml or vars/main.yml.
Specified values in vars/main.yml take priority.

| Variable                  | Type      | Default                                   | Comment                                           |
| ------------------------- |:---------:|:-----------------------------------------:|:-------------------------------------------------:|
| cuda_version              | str       | 11.5                                      | Cuda version that will be installed               |
| download_folder           | str       | /sbdata/software/download                 | Path of folder for downling run file              |
| toolkit_install_folder    | str       | /sbdata/software/apps                     | Path for folder to install toolkit in             |
| modulefile_folder         | bool      | /sbdata/software/apps/modulefiles/Core    | Path for containing modulefile if wanted          |
| create_lua_modulefile     | bool      | true                                      | True will create a lua modulefile                 |
| create_tcl_modulefile     | bool      | false                                     | True will create a tcl modulefile                 |


Dependencies
------------

No ansible collections needed.

Example Playbook
----------------

To run it type for example:
```
ansible-playbook run.yml --user=$ANSIBLE_USER --extra-vars "ansible_sudo_pass=$ANSIBLE_USER_PASSWORD" >> role_cuda_log.txt
```
or inside a playbook:
```
- hosts: localhost
  become: True
  roles:
    - role_slurm
```

License
-------

Apache License 2.0

Author Information
------------------

This role was created in 2021 by Kilian Schnelle, part of the Department of Structure Biology at the University of Osnabrueck.
