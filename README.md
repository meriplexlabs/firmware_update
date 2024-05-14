# Ansible Role for Cisco Device Management

This Ansible role is designed to manage firmware updates on Cisco network devices. It ensures proper firmware versions are applied, configures backups before updates, checks disk space, and updates firmware where needed.

## Features

- **Firmware Version Checking**: Compares current firmware against a baseline to determine update needs.
- **Configuration Backup**: Automatically backs up the device configuration before applying any updates.
- **Disk Space Validation**: Ensures sufficient disk space is available and logs devices with insufficient space.
- **Firmware Update**: Applies necessary firmware updates based on version comparisons.

## Requirements

- **Ansible 2.9+**: This role requires Ansible 2.9 or newer.
- **Network Access**: Must be able to access Cisco IOS devices over the network.
- **Credentials**: Requires administrative credentials for device management.

## Role Variables

This role utilizes the following variables, which you should define according to your network setup:

```yaml
firmware_versions: 
  $device_model1: "$firmware_file1"
  $device_model2: "$firmware_file2"
min_free_space_mb: 100  # Minimum free space in MB required to perform updates.
```

## Dependencies

None

## Example Playbook

```yaml
- hosts: cisco_switches
  gather_facts: no
  roles:
    - switch_update
```

## Executing the Playbook

```bash
ansible-playbook -i inventory.yml playbook.yml
```

## Contributing

Contributions to this role are welcome. Ensure that your contributions pass existing tests and include any necessary new tests to cover new features.

## Additional Information

For more detailed information on role usage and configuration, please refer to the official Ansible documentation applicable to Cisco device management.