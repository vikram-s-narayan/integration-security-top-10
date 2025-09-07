# ISF-5 Playbook: No Real-Time Token Activity Monitoring

## Risk
Stolen tokens look like normal API calls unless anomalies are flagged.

## Objective
Detect abnormal token use in near real-time.

## Steps
1. Inventory – Enable event logging.
2. Policy – Define thresholds (geo, volume).
3. Enforce – Alerts for bulk queries or TOR nodes.
4. Automate – SIEM rules for anomalies.
5. Review – Weekly incident review.

## Success Criteria
1. Alerts fire for abnormal patterns.
2. MTTD < 2h for token misuse.
