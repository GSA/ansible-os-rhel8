# Redhat 8 CIS Benchmark

A role to implement Center for Internet Security (CIS) controls for RHEL 8. It is based on [cis-security](https://github.com/dsglaser/cis-security)

## Role Variables

There are many role variables defined in ``./defaults/main.yml``.

**Hardening will be applied to the following configurations by default**:

- General Configurations (Section 1)
- Services Configurations (Section 2)
- Network Configurations (Section 3)
- Logging and Auditing Configurations (Section 4)
- Access, Authentication and Authorization Configurations (Section 5)
- System Maintenance Configurations (Section 6)

Above high level configurations and other fine-grained configurations can be enabled/disabled using variabled defined in in defaults/main.yml.

**The configuration will not**:

- Install and configure AIDE
- Install and configure NTP
- Configure the /etc/group wheel configurations

Other settings and services are listed. Please review to ensure they meet your organizational requirements.

## Dependencies

Ansible >= 2.7

## Example Playbook

```
---
- name: Harden Server
  hosts: all
  become: yes

  roles:
    - ansible-os-rhel8
```

## How to test locally

```
ansible-playbook playbook.yml --connection=local
```

## CircleCI Intergration

This role is used by an up-stream git repo. This repo itself doesn't have CI yet. 

## License

BSD.
