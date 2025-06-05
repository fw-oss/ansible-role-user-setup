# User-Setup

Creates all users defined by vars. Removes all undefined users

## Requirements

none

## Role Variables

Users have to be defined like this:

```yaml
users:
  - name: username
    comment: Some User
    groups: users, admin
    sudo: true
    ssh_keys:
      - ssh-rsa [...]
```

## Dependencies

Only default modules are used. No dependencies.

## Example Playbook

```yaml
- name: Set users
  hosts: all
  vars:
    users:
      - name: jenny
        comment: Some User
        groups: users, admin
        sudo: true
        shell: "/bin/bash"
        ssh_keys:
          - ssh-rsa [...]
    docker_users:
      - jenny
      - fritz
      - madeleine
  become: true
  roles:
    - role: user_setup
```

## License

MIT

## Author Information

