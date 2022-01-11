ansible-role-win-onedrive
=========

Installs Microsoft OneDrive


Role Variables
--------------

The default values for the variables are set in defaults/main.yml:

```yaml
onedrive_version: 21.230.1107.0004
onedrive_download_url: 'https://go.microsoft.com/fwlink/?linkid=844652'
onedrive_per_machine_install: false
onedrive_installer_arguments: "{{ onedrive_per_machine_install | bool | ternary('/allusers /silent', '/silent') }}"
onedrive_creates_path: 'C:\Program Files\Microsoft OneDrive\{{ onedrive_version }}'
```

Example Playbook
----------------

```yaml
---
- hosts: win10
  become: true
  gather_facts: true
  vars:
    onedrive_per_machine_install: true

  roles:
    - ansible-role-win-onedrive
```
