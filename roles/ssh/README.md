---
# Reference doc — auto-generated, do not edit by hand.
# Regenerate via: python3 manage/gen_role_readmes.py
namespace: mps
collection: users
role: ssh
---

# `mps.users.ssh`

Main entry point for the ssh role.

## Dependencies

- `mps.base.assert_debian13`
- `mps.base.identity`

## Example usage

```yaml
- hosts: all
  roles:
    - mps.users.ssh
```

## Role metadata

- **Min Ansible version**: `2.16.0`
- **License**: G, P, L, -, 3, ., 0, -, o, r, -, l, a, t, e, r
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 9
