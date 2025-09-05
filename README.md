# 🔐 Integration Security Top 10 (ISF)

The **Integration Security Top 10 (ISF)** is an open-source framework for securing **OAuth, API, and SaaS-to-SaaS integrations**. Inspired by the OWASP Top 10, it highlights the **most critical risks** and provides **practical guardrails** to reduce the blast radius of integration compromises.

---

## 🎯 Why ISF?
Modern enterprises run on integrations — Salesforce ↔ Slack, Google Workspace ↔ ServiceNow, Epic ↔ cloud storage. But as the 2025 Salesloft–Drift incident showed, a single weak integration can cascade into **hundreds of downstream breaches**.  
ISF exists to fix this gap: short, memorable, and actionable.

---

## 📜 The Top 10 Risks

1. **Excessive OAuth Scopes**  
   Require least privilege scopes. Avoid “full access” unless strictly necessary.

2. **Unbounded Token Lifetimes**  
   Rotate refresh tokens regularly. No perpetual tokens.

3. **Lack of Token Binding**  
   Bind tokens to client, device, or IP context. Enforce Proof-of-Possession (PoP).

4. **Centralized Token Storage Risks**  
   Encrypt and segment token stores. Monitor for compromise.

5. **No Real-Time Token Activity Monitoring**  
   Detect anomalies: new geos, bulk API queries, unusual patterns.

6. **Weak Vendor Due Diligence**  
   Evaluate SaaS vendors for integration security practices before onboarding.

7. **Insecure Integration Defaults**  
   Vendors must provide secure defaults: minimal scopes, IP allowlists, admin MFA.

8. **Blind Trust in Transitive Integrations**  
   Map and monitor downstream data flows (e.g. Slack → Google Drive → Salesforce).

9. **Missing Incident Response for Integrations**  
   Define playbooks for token revocation, scope rollback, customer notification.

10. **Opaque Auditability**  
    Ensure logs cover integration events and are exportable + tamper-evident.

---

## 🔗 Mappings to Existing Frameworks
ISF is **complementary** to existing standards. Each Top 10 item maps to NIST CSF, CIS Controls, and ISO 27001.  
👉 [See full mapping here](docs/ISF-Mappings.md)

---

## 🤝 Contributing
We welcome issues and pull requests!  
- Add real-world case studies.  
- Suggest improvements to controls.  
- Map ISF Top 10 to additional standards.  

---

## 📢 Attribution
ISF is maintained by **Vikram S. Narayan** and is open to community contributions :)  
Modeled after the success of the OWASP Top 10 — concise, practical, and open.

