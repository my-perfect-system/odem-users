---
# Reference doc — auto-generated, do not edit by hand.
# Regenerate via: python3 manage/gen_role_readmes.py
namespace: mps
collection: users
role: groups
---

# `mps.users.groups`

Main entry point for the groups role.

## Default variables

| Variable | Default | Description |
|---|---|---|
| `groups_enable_extract_from_users` | `true` | When true, scan resolved users and extract each user's C(group) and C(groups) fields as groups to ensure-present. |
| `groups_list` | `[]` | Explicit list of group dicts to manage. Each entry supports the sub-options below. |

## Dependencies

- `mps.base.assert_debian13`
- `mps.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - mps.users.groups
```

## Role metadata

- **Min Ansible version**: `2.16.0`
- **License**: G, P, L, -, 3, ., 0, -, o, r, -, l, a, t, e, r
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 8
