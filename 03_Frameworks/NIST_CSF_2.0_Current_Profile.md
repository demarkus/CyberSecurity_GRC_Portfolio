# NIST CSF 2.0 Current Profile & Prioritised Gaps

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> Current Profile assessment across GV.RR, ID.RA, PR.AA and DE.CM, with corrected risk-register mapping and a prioritised gap list.

## Full Current Profile Assessment (4 Subcategory Areas)

## Subcategory area: Roles, Responsibilities and Authorities (Govern → GV.RR)

**Field                     | Content**
__________________________________________________________________________________________________________________________________
**Outcome being assessed**  | Cybersecurity and access-control responsibilities are clearly assigned, communicated, and carried
                            | out by authorised personnel. 
__________________________________________________________________________________________________________________________________
**Evidence**                | Off-boarding RACI matrix assigning duties to the Owner, Shift Manager, and IT Contractor; Compliance
                            | Officer job description; Week 2 status scorecard showing named finding owners.
__________________________________________________________________________________________________________________________________**Evidence method**         | Inspection of the documented RACI matrix, role responsibilities, and scorecard.
__________________________________________________________________________________________________________________________________**Finding**                 | Roles and accountability are documented, including the Owner as Accountable for off-boarding. 
                            | However, the 31-hour access-revocation exception shows that assigned responsibilities were not
                            | followed consistently in practice.
__________________________________________________________________________________________________________________________________
**Rating**                  | **Partially Achieved** — governance responsibilities are defined, but available testing shows that 
                            | execution and follow-up are not yet consistently effective. 
__________________________________________________________________________________________________________________________________
**Gap to Target**           | Require formal approval of the RACI, introduce a mandatory off-boarding checklist, require written 
                            | completion confirmation from the IT Contractor, and periodically test whether assigned 
                            | responsibilities are being performed. 

## Subcategory area: Risk Assessment (Identify → ID.RA)

**Field                     | Content**
__________________________________________________________________________________________________________________________________
**Outcome being assessed**  | Cybersecurity, operational, compliance, and safety risks are identified, analysed, prioritised, 
                            | assigned to owners, and tracked.
__________________________________________________________________________________________________________________________________
**Evidence**                | Week 1 risk register containing risks such as R-003 off-boarding delay, R-004 POS password exposure,
                            | R-001 WordPress vulnerability, and R-021 slip-and-fall risk; findings classification memo; 
                            | remediation plans and scorecard.
__________________________________________________________________________________________________________________________________
**Evidence method**         | Inspection of the risk register, classification memo, remediation records, and status scorecard.
__________________________________________________________________________________________________________________________________
**Finding**                 | The café has identified and prioritised multiple risks using likelihood and impact reasoning, and 
                            | some risks have assigned owners and remediation actions. Evidence is limited regarding a formally
                            | approved review cadence and whether the full register is regularly updated when conditions change.
__________________________________________________________________________________________________________________________________
**Rating**                  | **Partially Achieved** — a functioning risk register and assessment process exist, but the evidence
                            | does not yet show a consistently governed and recurring risk-review process.
__________________________________________________________________________________________________________________________________**Gap to Target**           | Establish a documented quarterly risk-register review, record approval by the Owner, define when
                            | risks must be reassessed, and maintain clear links between each risk, control, finding, and
                            | remediation action.  

## Subcategory area: Identity Management, Authentication and Access Control (Protect → PR.AA)

**Field                     | Content**
__________________________________________________________________________________________________________________________________
**Outcome being assessed**  | Accounts requiring access to the POS system use unique identities and strong authentication, 
                            | including MFA.
__________________________________________________________________________________________________________________________________
**Evidence**                | POS Authentication Standard; control-testing workpaper testing all 12 active POS accounts; POS administrator
                            | user-list export showing MFA status.
__________________________________________________________________________________________________________________________________
**Evidence method**         | Inspection of the POS user-list export and authentication standard.
__________________________________________________________________________________________________________________________________
**Finding**                 | Nine of twelve active POS accounts had MFA enabled. Three accounts, including two recent users and 
                            | one backup manager account, did not meet the standard at the time of testing.
__________________________________________________________________________________________________________________________________
**Rating**                  | **Partially Achieved** — a measurable standard exists and most accounts comply, but MFA is not 
                            | consistently enforced across the full population.
__________________________________________________________________________________________________________________________________
**Gap to Target**           | Enable MFA on all remaining accounts and implement a system-level restriction preventing any POS
                            | account from becoming active before MFA enrolment is completed and verified.

## Subcategory area: Continuous Monitoring (Detect → DE.CM)

**Field                     | Content**
__________________________________________________________________________________________________________________________________
**Outcome being assessed**  | The cafe monitors its POS, email, network, endpoint-security, and backup systems for suspicious
                            | activity, control failures, and security alerts. 
__________________________________________________________________________________________________________________________________
**Evidence**                | Detect Target Profile statement recommending built-in alerts, weekly POS-log review, named alert
                            | ownership, and an incident log. No completed monitoring logs, alert-review records, or tested
                            | detection procedures were available. 
__________________________________________________________________________________________________________________________________
**Evidence method**         | Inspection of the Target Profile and portfolio artifacts for evidence that monitoring activities
                            | had been implemented and  performed.
__________________________________________________________________________________________________________________________________
**Finding**                 | The desired monitoring approach has been documented, but there is no evidence that alerts are 
                            | currently enabled, reviewed on a defined schedule, documented, or escalated. The artifact describes
                            | a future state rather than an operating control.
__________________________________________________________________________________________________________________________________
**Rating**                  | **Not Achieved** — the intended outcome is recognised, but no reliable evidence shows that 
                            | continuous monitoring currently  operates.
__________________________________________________________________________________________________________________________________
**Gap to Target**           | Enable affordable built-in alerts for failed logins, administrator changes, malware detections, 
                            | unusual POS activity, and backup failures; assign a reviewer; document weekly reviews; maintain
                            | an incident log; and test that alerts are received and investigated.

## Risk Register Mapping Correction

## Corrected Mapping: Risk Register → Identify, Risk Assessment (ID.RA)

The Fresh Brew Cafe risk register maps primarily to **Identify — Risk Assessment (ID.RA)** because it records identified threats and vulnerabilities, evaluates likelihood and impact, determines risk levels, and tracks selected risk responses. These activities align directly with ID.RA outcomes concerning the identification and recording of threats, assessment of likelihood and impact, prioritisation of risk, and tracking of risk responses.

It does **not primarily map to GV.RM**, because **Risk Management Strategy (GV.RM)** concerns the organisation-level rules that guide risk decisions — such as risk objectives, appetite, tolerance, response options, and the standard method used to calculate and prioritise risks.

> **Final mapping:** **Risk Register → ID.RA**
> **Reason:** The register documents and assesses individual risks, while **GV.RM** establishes the strategy and methodology governing how those assessments should be performed.

## Prioritized Gap List

### 1. Close the POS MFA gap — **PR.AA**

Enable MFA on the remaining **3 of 12 POS accounts** and prevent new accounts from becoming active before MFA enrolment is complete.

**Priority reason:** The likelihood is elevated because several active accounts rely only on passwords, and the potential magnitude is significant because compromised POS access could enable unauthorised transactions, refunds, or access to business information.

### 2. Establish basic security monitoring — **DE.CM**

Enable built-in alerts for failed logins, administrator changes, malware detections, unusual POS activity, and backup failures; assign an alert reviewer and maintain an incident log.

**Priority reason:** Detection is currently **Not Achieved**, meaning suspicious activity could remain unnoticed. The likelihood is meaningful because attacks and control failures may occur without warning, while the magnitude could be high if unauthorised access or data loss continues undetected.

### 3. Strengthen accountability for access controls — **GV.RR**

Formally approve the off-boarding RACI, implement a mandatory checklist, and require written confirmation that access has been revoked.

**Priority reason:** Responsibilities are documented, but the **31-hour off-boarding exception** shows that they are not consistently followed. The likelihood is moderate because the process relies on manual action, while the potential impact includes former employees retaining access to cafe systems.

### 4. Formalise recurring risk reviews — **ID.RA**

Introduce a quarterly risk-register review, document Owner approval, and maintain clear links between risks, controls, findings, and remediation actions.

**Priority reason:** The cafe already identifies and assesses risks, so the immediate likelihood of harm from this governance gap is lower than the active access and monitoring weaknesses. However, without regular reviews, risks may become outdated, overlooked, or poorly prioritised over time.

> **Priority order:** Active access exposure → missing detection capability → inconsistent accountability → risk-process improvement.
