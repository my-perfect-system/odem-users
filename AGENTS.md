# AGENTS.md — mps-users

User accounts, groups, SSH keys, sudoers. Every per-user role filters
`identity_users_resolved` (produced by the `mps.base.identity`
dependency) for its own opt-in users.

## Galaxy

- **namespace**: `mps`
- **name**: `users`
- **version**: `0.3.1`
- **dependencies**: `mps.base >=0.1.0`, `ansible.posix >=1.0.0`, `community.general >=1.0.0`

## Roles

| Role | Description | Complexity |
|---|---|---|
| `mps.users.users` | Create / remove user accounts. Root special-path handling via `chpasswd` / `chsh` / `chfn` / `chage` (avoids `usermod` PID-1 check). | 3 |
| `mps.users.groups` | Add / remove Unix groups; flat list of referenced groups built from each user's `group` and `groups` fields. | 2 |
| `mps.users.ssh` | Deploy SSH keys and authorized_keys (per user). Resolves `authorized_keys` from inline + `lookup('file')` sources. | 2 |
| `mps.users.sudo` | Manage per-user sudoers entries via `community.general.sudoers` (previously template + `visudo -cf`). Resolves `sudo.macros` inline to a flat command list per user. | 3 |

## Dependencies on `mps.base`

- Every role in this collection declares `mps.base.assert_debian13` + `mps.base.identity` in `meta/main.yml`.
- Role execution is gated by each role's `user_roles.<key>` flag (denylist model).

## Conventions

- **Distinct operations are distinct files** — `add.yml`, `del.yml`, `facts.yml` for groups/users; `add.yml`, `authorized_keys.yml`, `facts.yml` for ssh. Multi-file by design.
- **sudo is `community.general.sudoers` per user** — `/etc/sudoers.d/<sanitized-name>` files. Per-file `validate: visudo` was retired.
- **Root is special** — handled via `chpasswd` / `chsh` / `chfn` / `chage` because `usermod` refuses to modify PID-1.
