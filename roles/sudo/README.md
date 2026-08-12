---
# Reference doc — auto-generated, do not edit by hand.
# Regenerate via: python3 manage/gen_role_readmes.py
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
- **License**: G, P, L, -, 3, ., 0, -, o, r, -, l, a, t, e, r
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 6
