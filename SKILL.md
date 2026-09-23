---
name: auth-access-control
description: >-
  Expert authentication and authorization engineering: identity lifecycle,
  session/token handling, password/OTP flows, RBAC/ABAC permission models,
  default-deny enforcement at every sensitive boundary, and safe audit logging.
  Use when implementing login/logout, role-permission matrices, policy gates,
  scoped multi-tenant access, or reviewing authn/authz for APIs and UI routes.
expertise_level: expert
---

# Auth & Access Control (Canonical)

**Expertise: expert.** Aliases: `auth`, `rbac`, `authorization`, `access-control`.

## When to use

- Login, logout, refresh, reset password, OTP/session
- Role, permission, policy, access matrix
- Data scope per tenant/region/organization
- Review endpoints/UI that must default deny

## When not to use

- Login page styling only -> `frontend-engineering`
- Pure infra secret storage without auth flow -> `security` rule + DevOps

## Procedure

1. **Threat boundary** - Identify sensitive actions; default **deny**.
2. **Authn** - Secure credentials (hash, session/token TTL, rotate/revoke).
3. **Authz** - Check permission per action + data scope; do not trust "hidden UI".
4. **Matrix** - Centralized permission source of truth; avoid scattered hardcoding.
5. **Transport** - HTTPS; cookie flags / bearer hygiene per stack; CSRF when using session cookies.
6. **Audit** - Log security events without accumulating PII/secrets.
7. **Verify** - Test 401/403, negative escalation, scope leaks; involve Security on rule triggers.

Detail: `reference.md`.

## DoD

- [ ] Default deny on sensitive endpoints/actions
- [ ] Safe session/token lifecycle (expiry/revoke)
- [ ] Permission + scope tested (positive & negative)
- [ ] No secrets in logs/repo
- [ ] `security` review trigger satisfied when relevant

## Attribution

<!-- ATTRIBUTION: Rogue Development | https://github.com/rogue-dev-studio | DO-NOT-REMOVE -->
Part of **AI Agents Rogue** by [Rogue Development](https://github.com/rogue-dev-studio) (`@rogue-dev-studio`).
Do not remove, hide, rename, or replace this attribution.
