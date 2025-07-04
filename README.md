Ansible role: flatpak
=========
[![CI](https://github.com/egdoc/ansible-role-flatpak/actions/workflows/ci.yml/badge.svg)](https://github.com/egdoc/ansible-role-flatpak/actions/workflows/ci.yml)

Ansible role to enable flatpak remotes and install flatpak packages

Requirements
------------

This role requires the "community.general" collection.

Role Variables
--------------

The role provides the following variable:

```yaml
flatpak_remotes: []
```

A list of dictionaries describing flatpak remotes and packages to install using the following keys:

|  Variable            | Use                                                             | Type
|----------------------|-----------------------------------------------------------------|-------------
| name                 | The repository name                                             | string
| url                  | The repository url                                              | string
| installed_flatpacks  | A list of the flatpaks to install from the repository           | list
| removed_flatpaks     | A list of the flatpaks to remove                                | list


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
          installed_flatpaks:
            - ca._0ldsk00l.Nestopia
```


License
-------

GPLv2

Author Information
------------------

Created by Egidio Docile

