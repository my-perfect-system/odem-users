---
namespace: mps
collection: users
role: sudo
---

# `mps.users.sudo`

Main entry point for the sudo role.

## Default variables

| Variable | Default | Description |
|---|---|---|
| `sudo_macros` | `{ ADMIN_DEFAULT: …, ADMIN_DEBUG: …, ADMIN_MINIMAL: … }` | Mapping of macro names (referenced from C(sudo.macros) per user) to lists of command patterns that get expanded inline into each per-user sudoers file. |

## Dependencies

- `mps.base.assert_debian13`
- `mps.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - mps.users.sudo
```

## Role metadata

- **Min Ansible version**: `2.16.0`
- **License**: GPL-3.0-or-later
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 6

## Related files

- [`meta/main.yml`](meta/main.yml) — galaxy_info + role dependencies
- [`meta/argument_specs.yml`](meta/argument_specs.yml) — variable spec (the source of the variable table above)
- [`defaults/main.yml`](defaults/main.yml) — variable defaults (the source of the default values above)
