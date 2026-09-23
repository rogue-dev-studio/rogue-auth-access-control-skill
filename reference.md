# Auth & Access Control - Reference

## Authn

- Password: modern hash (bcrypt/argon2); never plain/reversible
- Server-side session or token with expiry + revoke list/rotation policy
- Brute-force: rate limit / lockout per threat model
- Logout invalidates server state / token family

## Authz models

| Model | When |
|-------|--------|
| RBAC | Stable roles + permission matrix |
| ABAC / policy | Attribute-based rules (owner, status, scope) |
| Scope | Query filter required on server, not FE only |

## UI vs API

- Hidden menu ≠ authorization
- FE `can()` is UX only; API must enforce again

## Anti-patterns

- Scattered string role checks without registry
- Trust `user_id` from body without binding to principal
- "All modules" permission accidentally synced to limited role
