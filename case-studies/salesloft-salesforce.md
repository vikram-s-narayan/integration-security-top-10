
# ISF Case Study: Salesloft–Drift OAuth Supply Chain Breach

## 1. Incident Overview

* **Incident name**: Salesloft–Drift OAuth Supply Chain Breach (GRUB1/UNC6395)
* **Date**: August 2025
* **Impact**: Over 700 Salesforce instances compromised, along with Google Workspace, Slack, and cloud storage integrations. Sensitive customer data, AWS credentials, and contact databases exfiltrated.
* **Attack vector**: Theft of OAuth tokens stored in Salesloft’s Drift platform.
* **Summary**: Threat actor exploited centralized OAuth token storage to gain persistent, MFA-bypassing access to downstream enterprise integrations.

---

## 2. Attack Chain Breakdown

* **Initial Access**: Unknown (likely admin credential compromise, phishing, or infra exploit).
* **Exploitation**: Theft of OAuth access and refresh tokens from Salesloft’s integration infrastructure.
* **Lateral Movement**: Tokens reused across 700+ Salesforce orgs, plus Gmail, Slack, and cloud storage.
* **Exfiltration / Impact**: Bulk API used to extract case records and sensitive data within minutes; tokens also harvested additional secrets (AWS keys, Snowflake tokens).

---

## 3. ISF Top 10 Mapping

| ISF Control                                  | Relevance | Prevent / Limit / Detect / Mitigate | Notes                                                                    |
| -------------------------------------------- | --------- | ----------------------------------- | ------------------------------------------------------------------------ |
| **#1: Excessive OAuth Scopes**               | ✅         | Limit                               | “Full access” scopes + Bulk API enabled rapid exfiltration.              |
| **#2: Unbounded Token Lifetimes**            | ✅         | Prevent                             | Refresh tokens valid indefinitely, no rotation.                          |
| **#3: Real-Time Token Monitoring**           | ✅         | Detect                              | Automated abuse (Python, aiohttp, Tor nodes) went unnoticed for 10 days. |
| **#4: Vendor Due Diligence**                 | ✅         | Prevent                             | Customers had no visibility into Salesloft’s security posture.           |
| **#9: Incident Response & Token Revocation** | ✅         | Mitigate                            | Token revocation was effective, but delayed by 10 days.                  |

---

## 4. Key Lessons Learned

* OAuth tokens = privileged credentials; without scope control and monitoring, they are equivalent to permanent master keys.
* Centralized SaaS integration platforms create **single points of systemic failure**.
* Detection lag (10 days) dramatically increased breach scope.
* Supply chain trust magnifies one vendor’s compromise across hundreds of organizations.

---

## 5. References

* [SOC Radar Incident Analysis]([url](https://socradar.io/salesloft-drift-breach-everything-you-need-to-know/))
* [Cloudflare incident report]([url](https://blog.cloudflare.com/response-to-salesloft-drift-incident/))


---
