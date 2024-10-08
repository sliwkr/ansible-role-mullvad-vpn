
# Ansible Role: Mullvad VPN

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
[![CI](https://github.com/sliwkr/ansible-role-mullvad-vpn/actions/workflows/ci.yml/badge.svg)](https://github.com/sliwkr/ansible-role-mullvad-vpn/actions/workflows/ci.yml)

Allows to install [Mullvad VPN](https://mullvad.net/en/download/vpn/linux)

## Requirements

* `min_ansible_version>=2.17`. See [meta/main.yml](./meta/main.yml) for details
* `ca-certificates` for adding a repository signing key. Installed as part of the role.

## Role Variables

* See [defaults](./defaults/main.yml) and vars for:
  * [debian](./vars/debian.yml)
* `ansible_os_family` from `ansible_facts` is used to determine [which installation flow to follow](./tasks/main.yml)

## Dependencies

* None

## Example Playbook

```yml
# playbook.yml, install
- hosts: all
  become: true
  gather_facts: true
  roles:
    - sliwkr.mullvad_vpn
```

```yml
# playbook.yml, install, another way
- hosts: all
  become: true
  gather_facts: true
  vars:
    mullvad_state: present
  roles:
    - sliwkr.mullvad_vpn
```

```yml
# playbook.yml, uninstall
- hosts: all
  become: true
  gather_facts: true
  roles:
    - role: sliwkr.mullvad_vpn
      vars:
        mullvad_state: absent
```

## License

GPL-3.0

## Author Information

[Krzysztof Sliwinski](https://github.com/sliwkr)
