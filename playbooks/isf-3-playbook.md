# ISF-3 Playbook: Lack of Token Binding

## Risk
Unbound tokens = replayable “fancy passwords.”

## Objective
Bind tokens to context (device, client, IP).

## Steps
1. Inventory – Identify systems not enforcing PoP.
2. Policy – All tokens require binding.
3. Enforce – Enable PoP in IdP/SaaS.
4. Automate – Block unbound tokens via gateway.
5. Review – Audit logs for replay attempts.

## Success Criteria
All high-privilege tokens context-bound.
