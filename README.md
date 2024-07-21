# Ansible Role: PiHole Update

This Ansible role automates the process of checking for and applying updates to PiHole installations.

## Role Description

The PiHole Update role performs the following tasks:

1. Checks for available updates for Pi-hole
2. Displays debug information if an update is available _(default variable set to false)_
3. Applies the update if one is available _(default variable set to false)_


## Role Variables

There are only 2 variables to set, by default they are false.

| Variable | Description |
| --- | --- |
| pihole_update_debug | Shows the Debug message from the command. This is a boolean value of `true` or `false`
| pihole_update_run | Requires `update available` to be found in the `command` output. Included is a control that you can set to state whether you want to update (if available) PiHole or not. This is a boolean value of `true` or `false`

## Example Playbook

Include this role in your playbook to ensure your PiHole installations are kept up-to-date:

```yaml
- name: Update PiHole Hosts
  hosts: pihole_servers
  gather_facts: false
  roles:
    - role: pihole_update
      pihole_update_debug: true
      pihole_update_run: true
```

## Requirements
1. Ansible 2.9 or higher
2. Pi-hole installed on target hosts

## License

MIT

## Author Information

This Role was created by [SixteenOne](https://twitter.com/sixteenone)
