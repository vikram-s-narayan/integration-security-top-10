# Integration Security Framework Top 10 (ISF Top 10)

The **Integration Security Top 10 (ISF)** is an open-source framework for securing **OAuth, API, and SaaS-to-SaaS integrations**. Inspired by the OWASP Top 10, it highlights the **most critical risks** and provides **practical guardrails** to reduce the blast radius of integration compromises.

---

## Why ISF?
Modern enterprises run on integrations — Salesforce ↔ Slack, Google Workspace ↔ ServiceNow, Epic ↔ cloud storage. But as the [2025 Salesloft–Drift incident showed]([url](https://socradar.io/salesloft-drift-breach-everything-you-need-to-know/)), a single weak integration can cascade into **hundreds of downstream breaches**.  
ISF exists to fix this gap: short, memorable, and actionable.

For more context, please see the [LinkedIn post]([url](https://www.linkedin.com/pulse/launch-integration-security-top-10-isf-vikramaditya-narayan-xraic/?trackingId=DIGDjEjZRaGWCGGZFlZdpw%3D%3D)).

---

## The ISF Top 10 Risks

1. **Excessive OAuth Scopes**  
   Broad, “full access” scopes turn every token into a skeleton key. Grant least privilege and deny high-risk scopes unless absolutely required.  

2. **Unbounded Token Lifetimes**  
   Tokens that never expire effectively bypass MFA and conditional access. Enforce rotation and contextual re-authentication for sensitive operations to ensure tokens don’t become permanent master keys.  

3. **Lack of Token Binding**  
   Unbound tokens can be replayed from anywhere. Bind them to client, device, or IP context, and enforce Proof-of-Possession (PoP).  

4. **Centralized Token Storage Risks**  
   A single token vault is a single point of systemic failure. Encrypt, segment, and continuously monitor repositories.  

5. **No Real-Time Token Activity Monitoring**  
   Stolen tokens look like normal API calls unless you’re watching. Detect anomalies such as unusual geos, bulk API queries, or automation patterns.  

6. **Weak Vendor Due Diligence**  
   One insecure SaaS vendor can compromise hundreds of customers. Assess their integration security posture before granting trust.  

7. **Insecure Integration Defaults**  
   Integrations often ship wide open. Vendors must enforce secure-by-default settings: minimal scopes, IP allowlists, admin MFA.  

8. **Blind Trust in Transitive Integrations**  
   Integrations call other integrations, creating hidden chains of trust. Map and monitor downstream data flows to avoid cascading risk.  

9. **Missing Incident Response for Integrations**  
   Without playbooks, revoking compromised tokens takes days, not minutes. Define rapid response for token revocation, scope rollback, and partner coordination.  

10. **Opaque Auditability**  
    If you can’t see it, you can’t secure it. Ensure integration logs are complete, exportable, and tamper-evident.  

---

## Contributing
We welcome issues and pull requests!  
- Add real-world case studies.  
- Suggest improvements to controls.  
- Map ISF Top 10 to additional standards.  

---

## Attribution
ISF is maintained by **Vikram S. Narayan** and is open to community contributions. 
Modeled after the success of the OWASP Top 10 — concise, practical, and open.

