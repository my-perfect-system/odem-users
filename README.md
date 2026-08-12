# `odem.users` Ansible Collection

User accounts, groups, SSH keys, sudoers management.

## Galaxy metadata

- **namespace**: `odem`
- **name**: `users`
- **version**: `0.3.1`
- **dependencies**: `odem.base`, `ansible.posix`, `community.general`

See [`galaxy.yml`](galaxy.yml) for the canonical values.

## Roles

| Role | Purpose |
|---|---|
| [`odem.users.users`](roles/users/README.md) | Create / remove Unix user accounts. Root special-path handling via `chpasswd` / `chsh` / `chfn` / `chage`. |
| [`odem.users.groups`](roles/groups/README.md) | Add / remove Unix groups; flat list of referenced groups built per-user. |
| [`odem.users.ssh`](roles/ssh/README.md) | Deploy SSH keys + authorized_keys per user. |
| [`odem.users.sudo`](roles/sudo/README.md) | Per-user sudoers management via `community.general.sudoers`. |

## Required catalog input

Every role consumes the per-user data model produced by `odem.base.identity`.
User opt-in is via the `user_roles.<key>: true` flag in `users_catalog`.

## Installation

```bash
ansible-galaxy collection install odem.users
ansible-galaxy collection install community.general
```

## Usage

```yaml
- hosts: all
  become: true
  vars:
    users_catalog:
      deploy:
        user_roles:
          terminal_bash: true
          terminal_python: true
          users_backup: true
        shell: /bin/bash
  roles:
    - odem.base.identity
    - odem.users.users
    - odem.users.groups
    - odem.users.ssh
    - odem.users.sudo
```

## Documentation

- [`AGENTS.md`](AGENTS.md) — developer conventions
- `roles/<role>/README.md` — per-role variable docs

## License

GPL-3.0-or-later
