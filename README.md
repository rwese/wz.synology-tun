# wz.synology-tun

Setup a service to load the tun modules on a synology nas to allow vpn and
similar services to run.

The service will run after `network-target`.

## Requirements

Nothing

## Role Variables

| Variable Name                | Type   | Purpose                                               | Default             | Required |
| ---------------------------- | ------ | ----------------------------------------------------- | ------------------- | -------- |
| `synology_tun__scripts_home` | String | location where the start/stop script should be placed | `/opt/synology_tun` | Yes      |
| `synology_tun__state`        | String | state, absent will uninstall the service              | `present, absent`   | No       |

## Dependencies

## Example Playbook

```yaml
---
- name: Setup Tun Service
  hosts:
    - synology
  become: true
  gather_facts: true
  roles:
    - wz.synology-tun
  vars:
    synology_tun__scripts_home: "/opt/synology_tun/"
    synology_tun__state: "present"
```

## License

MIT

## Author Information
