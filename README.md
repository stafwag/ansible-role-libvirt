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

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be.
