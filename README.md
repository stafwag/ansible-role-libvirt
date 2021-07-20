# Ansible Role: libvirt

An ansible role to to install libvirt/KVM packages and enable the libvirtd
service.

## Requirements

### Supported platforms

* Archlinux
* Debian
* Centos
* Fedora
* RedHat
* Rocky
* Suse

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
