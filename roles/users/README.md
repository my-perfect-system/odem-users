---
# Reference doc — auto-generated, do not edit by hand.
# Regenerate via: python3 manage/gen_role_readmes.py
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
- **License**: G, P, L, -, 3, ., 0, -, o, r, -, l, a, t, e, r
- **Platforms**: Debian (trixie)
- **Tasks file lines**: 8
