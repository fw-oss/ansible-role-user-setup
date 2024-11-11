# Deploy-Users

Creates all users defined by vars. Removes all undefined users exept the ansible-user.

## Requirements

none

## Role Variables

Users have to be defined like this:

```yaml
users:
  - username:
    name: username
    comment: Some User
    groups: users, admin
    sudo: true
    ssh_authorized_keys:
      - ssh-rsa [...]
```

## Dependencies

Only default modules are used. No dependencies.

## Example Playbook

```yaml
- hosts: all
  vars:
    users:
      - username:
        name: username
        comment: Some User
        groups: users, admin
        sudo: true
        ssh_authorized_keys:
          - ssh-rsa [...]
  become: true

  roles:
    - role: deploy_users
```

## License

MIT

## Author Information

