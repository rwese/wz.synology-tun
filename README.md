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

This role is more meant to be added to an role but can be also used to install an updater for exiting docker-composes.

    - hosts: synology
      roles:
         - role: wz.synology-tun,
           vars:
            synology_tun__scripts_home: 'docker-compose-project'
            synology_tun__state: 'present'

## Example Role Task

    - name: trigger wz.synology-tun role
      include_role:
        name: wz.synology-tun
      vars:
        synology_tun__scripts_home: 'docker-compose-project'
        synology_tun__state: 'present'

## License

MIT

## Author Information
