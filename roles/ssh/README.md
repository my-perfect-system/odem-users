---
namespace: odem
collection: users
role: ssh
---

# `odem.users.ssh`

Main entry point for the ssh role.

## Dependencies

- `odem.base.common`
- `odem.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - odem.users.ssh
```

## Role metadata

- **Min Ansible version**: `2.16.0`
- **License**: GPL-3.0-or-later
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 9

## Related files

- [`meta/main.yml`](meta/main.yml) — galaxy_info + role dependencies
- [`meta/argument_specs.yml`](meta/argument_specs.yml) — variable spec (the source of the variable table above)
- [`defaults/main.yml`](defaults/main.yml) — variable defaults (the source of the default values above)
