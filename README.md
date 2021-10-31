# Ansible Role: basic_iptables_firewall

An ansible role to set up a basic iptables firewall.
The firewall scripts and sample template are based on 
[https://wiki.debian.org/DebianFirewall](https://wiki.debian.org/DebianFirewall)


## Requirements

* A GNU/Linux system
* systemd
* iptables

## Role Variables

### Playbook related variables and templates

#### Variables

* **firewall**: "namespace"
  * **template**: required. The firewall template

### Templates

* **standalone.j2**: sample template for a standalone system.
  This template will block all incoming traffic. Might be too secure if you want to manage your system with Ansible :-)
  
## Dependencies

None

## Example Playbooks

```
---
- name: Setup Firewall
  hosts: myworkstation
  become: true
  roles:
    - role: stafwag.basic_iptables_firewall
      vars:
        firewall:
          template:
            standalone.j2

```


## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be.
