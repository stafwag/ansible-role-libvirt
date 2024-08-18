# Ansible Role: libvirt

An ansible role to install libvirt/KVM packages and enable the libvirtd
service.

## Requirements

### Supported GNU/Linux Distributions

* Archlinux
* AlmaLinux
* Debian
* Centos
* Fedora
* RedHat
* Rocky
* Suse
* Ubuntu

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
- name: Install libvirt 
  gather_facts: true 
  become: true
  hosts: kvm_hosts
  roles:
    - role: stafwag.libvirt
```

### Install libvirt packages with include_role

```
---
- name: Install libvirt 
  gather_facts: true 
  hosts: all
  become: true
  tasks:
    - name: Install the requirements
      include_role:
        name: "{{ item }}"
        tasks_from:
          install
      with_items:
        - stafwag.libvirt
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, personal website: https://www.wagemakers.be, my company: https://mask27.dev .
