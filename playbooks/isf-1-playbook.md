# ISF-1 Playbook: Excessive OAuth Scopes

## Risk
Broad, “full access” scopes turn every token into a skeleton key. Grant least privilege and deny high-risk scopes unless absolutely required.

## Objective
Grant least privilege and deny high-risk scopes unless absolutely necessary.

## Steps

1. Inventory – Export all app scopes; flag “all” or admin scopes.
2. Policy – Create allow/deny catalog.
3. Enforce – Restrict app scopes in IdP/SaaS consoles.
4. Automate – Block PRs with disallowed scopes in CI/CD.
5. Review – Monthly audits.

## Success Criteria

1. No apps with blanket “all” scopes.
2. Exceptions documented and approved.
