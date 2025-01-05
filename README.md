# Ansible Role: libvirt

An ansible role to install libvirt/KVM packages and enable the libvirtd
service.

## Requirements

### Supported GNU/Linux Distributions

* Archlinux
* AlmaLinux
* Centos
* Debian
* Fedora
* RedHat
* Rocky
* Suse
* Ubuntu

## Installation

### Ansible galaxy

The role is available on [Ansible Galaxy](https://galaxy.ansible.com/ui/standalone/roles/stafwag/libvirt/).

To install the role from Ansible Galaxy execute the command below.

```bash
$ ansible-galaxy role install stafwag.libvirt
```

### Source Code

If you want to use the source code directly.

Clone the role source code.

```bash
$ git clone https://github.com/stafwag/ansible-role-libvirt stafwag.libvirt
```

and put it into the [role search path](https://docs.ansible.com/ansible/2.4/playbooks_reuse_roles.html#role-search-path)

## Role tasks, variables and templates

### Tasks

* **install**

    All installation-related tasks are defined in the ```install``` playbook. This allows you to install the
    required packages and start/enable the required service with ```tasks_from``` in the ```include_role```,
    ```import_role```, … ansible modules.

    See example below.

### Tags

* **install**

  Install the required packages.


## Example Playbooks

### Install libvirt packages
 
```
---
- name: Install libvirt
  gather_facts: true
  become: true
  hosts: localhost
  roles:
    - role: stafwag.libvirt
```

### Install libvirt packages with include_role

```
---
- name: Install libvirt
  gather_facts: true
  hosts: localhost
  become: true
  tasks:
    - name: Install the requirements
      ansible.builtin.include_role:
        name: "{{ _role }}"
        tasks_from:
          install
      with_items:
        - stafwag.libvirt
      loop_control:
        loop_var: _role
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, personal website: https://www.wagemakers.be, my company: https://mask27.dev .
