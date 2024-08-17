
# Ansible Role: Mullvad VPN

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

Allows to install [Mullvad VPN](https://mullvad.net/en/vpn)

## Requirements

* `min_ansible_version>=2.17`. See [meta/main.yml](./meta/main.yml) for details

## Role Variables

* See [defaults](./defaults/main.yml) and vars for:
  * [debian](./vars/debian.yml)
* `ansible_os_family` from `ansible_facts` is used to determine [which installation flow to follow](./tasks/main.yml)

## Dependencies

* None

## Example Playbook

```yml
# install
- hosts: all
  become: true
  roles:
    - sliwkr.mullvad_vpn
```

```yml
# uninstall
- hosts: all
  become: true
  roles:
    - sliwkr.mullvad_vpn
      mullvad_state: absent
```

## License

GPL-3.0

## Author Information

[Krzysztof Sliwinski](https://github.com/sliwkr)
