# Control Testing Workpapers

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> Audit workpapers testing POS MFA enforcement (inspection) and leaver access revocation (re-performance), with a severity explanation for management.

## Test 1: POS MFA Enforcement (Inspection)

**Control ID:** R-004-MFA

**Control Description:** Every active Fresh Brew Cafe POS user account must have multi-factor authentication enabled in line with the POS Authentication Standard.

**Test Procedure:** Inspection — obtained and reviewed the POS administrator account report generated on 25 July 2026, focusing on the MFA enrolment status of each active user.

**Population:** 12 active POS user accounts.

**Sample:** 100% of the population — all 12 accounts were tested because the number of active users was small.

**Evidence Obtained:** `FreshBrew_POS_MFA_Report_20260726.csv` (simulated evidence), containing usernames, account status, assigned role, and MFA configuration status.

**Result:** **EXCEPTION** — 9 of the 12 active accounts were recorded as **“MFA Active.”** Three recently created cashier accounts were marked **“Pending Enrolment.”** 

**Conclusion:** The control is appropriately designed because the standard requires MFA for all POS accounts; however, it is **not operating effectively across the full population**. Management should enable MFA on the three affected accounts within **24 hours**, restrict their access until configuration is complete, and introduce a system check that prevents a new POS account from becoming active before MFA enrolment has been verified.

## Test 2: Leaver Access Revocation (Re-performance)

**Control ID:** R-003-OFFBOARDING

**Control Description:** All terminated employees must have their POS, email, WiFi, and other cafe system access revoked within **24 hours** of their termination time, in accordance with the employee off-boarding RACI matrix.

**Test Procedure:** Inspection (timestamp comparison) and Re-performance (independent login attempts) — selected terminated employees and independently recalculated the time between each employee’s recorded termination and account-disablement timestamps. I then personally attempted to sign in to the POS and staff WiFi using each former employee’s account, checked whether any existing POS sessions remained active, and confirmed that the accounts could not reset their passwords or regain access.

**Population:** 4 employees terminated between 1 June 2026 and 26 July 2026.

**Sample:** 100% of the population — all four terminated employees were tested because the population was small.

**Evidence Obtained:** Employee termination forms, `POS_Access_Log_20260726.csv`, account-disablement timestamps, staff WiFi user list, password-reset test results, and screenshots showing the rejected login attempts.

**Result:** **EXCEPTION** — three of the four terminated employees had all identified access revoked within 24 hours, and my independent login attempts were rejected. One employee’s POS account was disabled **31 hours and 20 minutes** after termination, exceeding the required period by **7 hours and 20 minutes**. The employee’s WiFi access had also remained active until the POS account was disabled. No transactions were recorded after termination.

**Conclusion:** The control is **designed effectively but is not fully operating effectively**, because one of the four terminated employees retained system access beyond the required 24-hour period. The Owner, as the Accountable person (A), should require the Shift Manager (I) to submit the off-boarding request immediately when termination occurs and require the IT Contractor (R) to confirm access revocation in writing. Management should also introduce an automated alert when termination access has not been revoked within **12 hours**, allowing corrective action before the 24-hour deadline.

## Severity Explanation for Management

> *Scenario question: if testing had found 5 of 12 accounts without MFA (instead of the actual 3), how would the severity and response change?*

(a) Finding that **5 of 12 POS accounts do not have MFA enabled** is significantly more serious than finding only two non-compliant accounts. Five accounts represent almost half (42%) of all active POS users, which suggests that the problem is not an isolated onboarding mistake but a broader failure in how the authentication control is being implemented and monitored. At 2 exceptions, temporary risk is tolerable while the fix happens; at 5, the exposure is large enough that we shouldn't wait even 48 hours — restrict access now, fix after."

The risk is also greater because an attacker would have five separate accounts that could potentially be accessed using only a stolen, guessed, or shared password. Since the POS system processes payments and contains sensitive business information, one compromised account could be used to perform unauthorised transactions, issue improper refunds, change records, or disrupt cafe operations. The larger number of unprotected accounts increases both the likelihood of an incident and the difficulty of identifying which employee was responsible.

(b) **Immediate next step**

Management should treat the five accounts as urgent exceptions and require MFA to be configured immediately. Until enrolment is completed, the accounts should either be temporarily disabled or restricted to the minimum access necessary. The cafe should also check recent login and transaction records for unusual activity and confirm that the affected passwords have not been shared or written down. 

**Longer-term fix**

The cafe should change the onboarding process so that a POS account cannot be activated until MFA enrolment has been completed and verified. MFA configuration should become a mandatory day-one onboarding task, with the Shift Manager responsible for confirming completion and the Owner reviewing a monthly report of all active accounts and their MFA status.

This would move the cafe away from relying on manual follow-up and create a preventive control that stops non-compliant accounts from becoming active in the first place.
