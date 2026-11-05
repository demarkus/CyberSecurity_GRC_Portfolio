# Recovery: RTO/RPO, Ransomware Restore Validation & CSF Coverage

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> RTO/RPO for three systems, a yes/no recovery validation checklist for a ransomware restore, and an honest six-function coverage assessment.

## Define RTO and RPO for Three Café Systems
### RTO and RPO for Three Fresh Brew Cafe Systems

| System | RTO | RPO | Business Justification |
|---|---|---|---|
| **POS System** | **2 hours** | **15 minutes** | The POS is critical to daily revenue. If unavailable for more than 2 hours,staff may struggle to process sales, refunds, and orders, causing queues and lost customers. Losing more than 15 minutes of transaction data could create payment, inventory, and reconciliation problems. |
| **Business Email** | **4 hours** | **1 hour** | Email supports suppliers, staff communication, invoices, and customer enquiries, but the café can continue serving customers during a short outage. A four-hour recovery window is therefore reasonable, while limiting data loss to one hour reduces the chance of losing important supplier or operational communications. |
| **Café Server / Business Data Backups** | **8 hours** | **24 hours** | The server may contain business records, reports, staff documents, and operational data, but the café can temporarily continue core service without immediate server access. Recovery within the same business day is appropriate, while a daily backup means the café accepts losing at most one day of recently changed data. |

### Priority

**POS → Email → Server/Backups**

The POS receives the most aggressive recovery objectives because its failure directly affects the cafe’s ability to generate revenue. Email and the server are important, but the cafe can operate manually for a limited period while those systems are restored.

## Recovery Validation Checklist

| # | Validation check | Pass/Fail |
|---|---|---|
| **1** | Confirm the selected backup was created **before the ransomware infection** and that the backup file passes its integrity/checksum verification. | ☐ Pass ☐ Fail |
| **2** | Restore the server into a **clean, isolated environment** and confirm the operating system starts without errors. | ☐ Pass ☐ Fail |
| **3** | Run a full malware/endpoint-security scan and confirm **no ransomware, malicious files, or persistence mechanisms are detected**. | ☐ Pass ☐ Fail |
| **4** | Confirm critical cafe data — such as sales records, staff documents, supplier information, and business files opens correctly and matches the expected backup date. | ☐ Pass ☐ Fail |
| **5** | Verify that compromised passwords, administrator credentials, and service accounts have been **reset or replaced** before reconnecting the server to the production network. | ☐ Pass ☐ Fail |
| **6** | Test critical server functions and confirm authorised users can access required files and services while unauthorised or terminated accounts cannot log in. | ☐ Pass ☐ Fail |
| **7** | Reconnect the server only after the above checks pass, then complete a **new successful backup** and verify that the backup job reports no errors. | ☐ Pass ☐ Fail |

> **Recovery is approved only when all critical checks pass; simply restoring the backup and turning the server on is not sufficient.**

## Full Six-Function Coverage Table
### Current Six-Function Coverage Table

**NIST CSF | What is geniunely built                            | Current               | What is still thin/missing**

| Function |  | Assessment |  |
|---|---|---|---|
| **Govern** | Risk ownership and escalation rules; Off-boarding RACI; Compliance Officer responsibilities; findings severity classifications; remediation plans; leadership status scorecard; early ISO SoA work. | **Partially Achieved — strongest area** | Governance artifacts exist, but several are newly created and there is limited evidence that management reviews, approves, and follows them consistently over time. The repeated off-boarding failure shows that documented accountability does not always translate into effective execution. |
| **Identify** | Week 1 risk register; likelihood × impact assessments; prioritised gap list; Current/Target Profile work; NIST/CIS/ISO mappings; identification of asset-inventory and physical-security gaps. | **Partially Achieved** | Risks are being identified and prioritised, but there is no complete enterprise asset inventory and limited evidence of recurring, formally scheduled risk-assessment cycle. |
| **Protect** | POS Authentication Policy/Standard/Procedure; MFA control and workpaper; off-boarding process; WordPress patching; RBAC design; physical-security requirements identified; backup expectations. | **Partially Achieved — reasonably developed** | Testing found **3 of 12 POS accounts without MFA**, and off-boarding did not consistently meet the 24-hour standard. Physical security and secure-configuration controls are also still immature. Protect is therefore documented better than it is consistently operating. |
| **Detect** | Monitoring Policy, Standard and Procedure; identified POS/email/router/antivirus/backup log sources; baseline concept; Detection Log with investigated events and escalation criteria. | **Partially Achieved — newly built** | The monitoring design is credible, but most evidence is still *designed rather* *than proven over time*. The cafe needs several consecutive weeks of completed reviews, retained evidence, tested alerts, and proof that unusual events are consistently investigated and closed. |
| **Respond** | POS compromise Incident Response Policy/Standard/ Procedure; defined response roles and authorities; response-time expectations; containment → eradication → recovery workflow; full terminated-account incident walkthrough; mid-incident Owner communication. | **Partially Achieved — design exists, operating evidence limited** | The response process is documented and scenario-tested, but there is little evidence of repeated real-world or tabletop execution. Response contacts, decision authority, evidence preservation, escalation, and communications should be exercised and measured before calling this fully effective. |
| **Recover** | Defined RTO/RPO for POS, email and server/backups; ransomware server recovery-validation checklist; backup-failure detection entry; principles for recovery validation and “recover better.” | **Partially Achieved still one of the thinner functions** | Recovery requirements are now documented, but there is not yet strong evidence of successful backup restoration tests, achievement of defined RTO/RPO targets, repeated recovery exercises, or management sign-off after validation. A backup existing is not yet proof that recovery works. |

### Overall Position

**Strongest:** Govern and Protect
**Developing:** Identify
**New but not yet proven:** Detect, Respond and Recover

The portfolio now touches **all six CSF Functions**, which is a significant improvement from the earlier position where Detect was essentially absent. However, the important distinction is:

> **Coverage does not equal effectiveness.**

Fresh Brew Cafe has moved from several functions being **undocumented** to having credible policies, standards, procedures, workpapers and plans. The next stage is no longer mainly document creation — it is generating **operating evidence**: repeated monitoring reviews, incident exercises, access-control retests, successful restoration tests, and proof that corrective actions remain effective over time.
