Ansible role: flatpak
=========

Ansible role to enable flatpak remotes and install flatpak packages

Requirements
------------

None

Role Variables
--------------

The role provides the following variable:

```yaml
flatpak_remotes: []
```

A list of dictionaries describing flatpak remotes and packages to install
from them using the following keys:

|  Variable | Use                                                             | Type
|-----------|-----------------------------------------------------------------|-------------
| name      | The repository name                                             | string
| url       | The repository url                                              | string
| method    | The method to use for the installation (system vs user)         | string
| user      | The user to install the package for if using the "user" method  | string
| packages  | A list of the packages to install from the repository           | list

Dependencies
------------

None

Example Playbook
----------------

Installing the MAME flatpak from flathub for the foo user:

```yaml
- hosts: workstations
  roles:
    - role: egdoc.flatpak
      become: true
      flatpak_remotes:
        - name: flathub
          url: https://dl.flathub.org/repo/flathub/flathub.flatpakrepo
          method: user
          user: foo
          packages:
            - org.mamedev.MAME
```


License
-------

GPLv2

Author Information
------------------

Created by Egidio Docile

