---
namespace: mps
collection: users
role: users
---

# `mps.users.users`

Main entry point for the users role.

## Default variables

| Variable | Default | Description |
|---|---|---|
| `users_enable_print_passwords_plaintext` | `false` | Print generated passwords and hashes to stdout (debug only). |

## Dependencies

- `mps.base.assert_debian13`
- `mps.users.groups`
- `mps.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - mps.users.users
```

## Role metadata

- **Min Ansible version**: `2.16.0`
- **License**: GPL-3.0-or-later
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 8

## Related files

- [`meta/main.yml`](meta/main.yml) — galaxy_info + role dependencies
- [`meta/argument_specs.yml`](meta/argument_specs.yml) — variable spec (the source of the variable table above)
- [`defaults/main.yml`](defaults/main.yml) — variable defaults (the source of the default values above)
