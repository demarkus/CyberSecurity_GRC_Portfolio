# Deficiency Classification & Remediation

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> Severity classification of control-testing findings, aggregation assessment and a findings memo with remediation steps.

## Classification Memo

**To:** Fresh Brew Cafe Owner
**Subject:** Classification of Identity and Access Control Findings
**Date:** 28 July 2026

### Finding 1: MFA Not Enabled on 3 of 12 POS Accounts

**Classification:** **Significant Deficiency**

Three of the twelve active POS accounts did not have MFA enabled, meaning **25% of the active account population** failed to meet the POS Authentication Standard. The three accounts belonged to cashiers awaiting enrolment. 

The **likelihood** of unauthorised access is more than remote because these accounts can be accessed using only a password. Passwords may be guessed, stolen, reused, shared, or exposed. 

The potential **magnitude** is meaningful because a compromised POS account could be used to process unauthorised transactions, issue refunds, change records, or access sensitive sales information. However, there is no evidence that the accounts were compromised or that fraud or financial loss occurred.

This is therefore more serious than an isolated control deficiency and deserves the Owner’s attention, but it does not rise to a material weakness because there is no evidence of widespread compromise, major loss, or a reasonable possibility of a severe undetected event.

### Finding 2: One of Four Terminated Employees Retained Access Beyond 24 Hours

**Classification:** **Control Deficiency**

One of the four terminated employees tested retained POS and staff WiFi access for **31 hours and 20 minutes**, exceeding the required 24-hour revocation period by **7 hours and 20 minutes**.

The **likelihood** of misuse was present because the former employee could potentially have accessed cafe systems during the delay. However, the delay was limited, the other three off-boardings were completed on time, and no transactions or suspicious activity were identified after termination.

The potential **magnitude** could have been serious if the former employee had used the account maliciously, but the actual exposure was limited to one employee and a relatively short period. The finding therefore represents a failure in the operation of the off-boarding control, but it is not severe enough on its own to be classified as a significant deficiency.

### Aggregation Assessment

When considered together, the findings indicate a broader weakness in the cafe’s **identity and access management controls**. The MFA exception affects how users are authenticated, while the off-boarding exception affects how access is removed when it is no longer required.

The two findings increase the overall risk because they show weaknesses at both ends of the account lifecycle:

* Some active accounts are not adequately protected.
* Some former employees may retain access longer than permitted.
* Both controls depend heavily on manual follow-up.
* Management monitoring did not identify the exceptions before testing.

**Aggregated classification:** **Significant Deficiency**

Together, the findings suggest that access-control failures are not purely isolated incidents. They show that the cafe’s processes for creating, protecting, reviewing, and removing accounts are not operating consistently. This combined weakness requires prompt attention from the Owner and a coordinated remediation plan.

The combined findings do not currently constitute a material weakness because there is no evidence of unauthorised transactions, widespread account compromise, prolonged former-employee access, or a major financial or operational loss. The classification could become more severe if additional testing identifies more affected systems, privileged accounts, repeated off-boarding delays, or evidence that access was misused.

### Overall Conclusion

Finding                                       | Individual classification 
--------------------------------------------- | ------------------------- 
Three of twelve POS accounts without MFA      | Significant Deficiency    
One of four off-boardings completed late      | Control Deficiency        
Combined identity and access control weakness | Significant Deficiency    

Management should treat the combined issue as a priority by enabling MFA on all active accounts, disabling non-compliant accounts until enrolment is complete, automating off-boarding notifications, and performing monthly reviews of active accounts, MFA status, and terminated-user access.

## Remediation Plan

**Finding Reference:** R-003-OFFBOARDING — One of four terminated employees retained POS and staff WiFi access for **31 hours and 20 minutes**, exceeding the required 24-hour revocation period by **7 hours and 20 minutes**.

**Root Cause:** The off-boarding process relied on the Manager manually notifying the IT Contractor, with no formal checklist, automated alert, or documented confirmation that all access had been revoked within the required period.

**Interim Mitigation:** Immediately disable the former employee’s remaining access, review all recently terminated employees to confirm that no active accounts remain, and require the Manager to notify both the Owner and IT Contractor as soon as any termination occurs.

**Permanent Fix:** Implement a formal off-boarding checklist requiring the Manager to submit an access-revocation request immediately after termination. The IT Contractor must disable POS, WiFi, email, and other system access and provide written confirmation. An alert must be sent to the Owner if revocation has not been completed within **12 hours**.

**Owner:** Cafe Owner — accountable for ensuring that the revised off-boarding process is implemented and consistently followed.

**Target Date:** 5 August 2026.

**Retest Date:** 5 September 2026 — test all employee terminations occurring after implementation and confirm that every relevant account was disabled within 24 hours, with supporting timestamps and written completion evidence.

## Findings Summary Memo to the Owner

## Findings Summary Memo

**To:** Fresh Brew Cafe Owner
**From:** Mark Yeboah Opoku (GRC Analyst)
**Subject:** Summary of POS Access-Control Findings
**Date:** 28 July 2026

### Overall Risk Posture

Fresh Brew Cafe’s identity and access controls are generally defined, but testing identified gaps in both account protection and employee off-boarding. The issues do not currently indicate a material weakness, as no unauthorised transactions, confirmed compromise, or major financial loss was identified. However, the findings show that access controls are not operating consistently and require timely corrective action.

### Finding 1: MFA Not Enabled on 3 of 12 POS Accounts

**Classification:** Significant Deficiency

Three active POS accounts did not have MFA enabled, representing 25% of the tested population. This increases the risk that stolen, shared, or guessed passwords could be used to gain unauthorised access. The issue is significant because it affects multiple accounts, and suggests that MFA enrolment is not consistently enforced.

**Recommended action:** Enable MFA on all three accounts immediately, restrict access until enrolment is complete, and require MFA setup before any new POS account becomes active.

### Finding 2: Delayed Revocation of Terminated Employee Access

**Classification:** Control Deficiency

One of four terminated employees retained POS and WiFi access for 31 hours and 20 minutes, exceeding the required 24-hour period. No suspicious activity was identified, and the other three accounts were revoked on time. The issue appears to be caused by reliance on manual notification and follow-up.

**Recommended action:** Introduce a formal off-boarding checklist, require immediate notification to the IT Contractor, and alert the Owner if access has not been revoked within 12 hours.

### Recommended Next Steps

Management should prioritise the MFA issue because it affects several active users and presents the greater immediate exposure. The off-boarding process should also be strengthened to prevent future delays. Both controls should be retested after remediation to confirm that MFA is enabled for all active accounts and that terminated-user access is consistently revoked within 24 hours.
