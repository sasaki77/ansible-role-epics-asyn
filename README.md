# Ansible Role: EPICS asyn

Installs EPICS asyn on RHEL/CentOS.

## Requirements

- ansible >= 2.3

## Role Variables
Refer to `defaults/main.yml` in detail.
```
epics_asyn_module:
  name: "asyn"
  type: "soft"
  ver: "4-31"
  url: "https://www.aps.anl.gov/epics/download/modules/asyn4-31.tar.gz"
  unarchived_name: "asyn4-31"
  configure_release:
      - {name: "EPICS_BASE", path: "{{ epics_base_name }}", reg: "^(.*)EPICS_BASE(.*)=(.*)$"}
      - {name: "SNCSEQ", path: "{{ epics_modules_name }}/soft/seq/{{ seq.ver }}", reg: "^(.*)SNCSEQ(.*)=(.*)$"}
```

## Dependencies

- [ansible-role-epics-base](https://github.com/sasaki77/ansible-role-epics-base)
- [ansible-role-epics-seq](https://github.com/sasaki77/ansible-role-epics-seq)

## Example Playbook
```
- hosts: epics-base
  roles:
    - role: ansible-role-epics-base
    - role: ansible-role-epics-seq
    - role: ansible-role-epics-asyn
```

## License

None.

## Author Information

This role was created by Shinya Sasaki.
