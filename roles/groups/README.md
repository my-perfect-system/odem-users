---
namespace: odem
collection: users
role: groups
---

# `odem.users.groups`

Main entry point for the groups role.

## Default variables

| Variable | Default | Description |
|---|---|---|
| `groups_enable_extract_from_users` | `true` | When true, scan resolved users and extract each user's C(group) and C(groups) fields as groups to ensure-present. |
| `groups_list` | `[]` | Explicit list of group dicts to manage. Each entry supports the sub-options below. |

## Dependencies

- `odem.base.assert_debian13`
- `odem.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - odem.users.groups
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
