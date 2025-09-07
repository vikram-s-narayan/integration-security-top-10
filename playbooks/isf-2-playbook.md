# ISF-2 Playbook: Unbounded Token Lifetimes & Hygiene

## Risk
Tokens that never expire bypass MFA; dormant apps become forgotten backdoors.

## Objective
Enforce short lifetimes and cleanup of unused tokens/apps.

## Steps
1. Inventory – List tokens, age, scopes, last used.
2. Policy – Access tokens ≤1h; refresh tokens ≤30d.
3. Enforce – Require re-auth for sensitive scopes.
4. Automate – Script to revoke unused tokens >30d.
5. Review – Quarterly cleanup.

## Success Criteria
1. No tokens older than policy.
2. Dormant apps pruned.
