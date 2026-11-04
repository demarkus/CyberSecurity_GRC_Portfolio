# Data Retention Schedule & Secure Disposal Procedure (POPIA s14)

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> Retention schedule with legal/business basis (unverified bases flagged), a restriction-of-processing scenario and a secure disposal procedure.

*Write the actual Data Retention & Disposal Standard — the real artifact, not a description of one*.

## Retention Schedule
|**Record Category           | Retention Period      | Legal/Business Basis                       | Disposal Method**
__________________________________________________________________________________________________________________________________
|**1. Financial & tax**      | **5 years**           | **Verified legal basis:** SARS generally   | **Digital:** secure deletion/
|**records** — invoices,     |                       | requires relevant tax records to be        | cryptographic erasure where 
| receipts, accounting       |                       | retained for **5 years**. Longer           | appropriate.
| records, tax-supporting    |                       | retention may apply where an audit,        | **Physical:** cross-cut
| documents                  |                       | investigation, objection or appeal is      | shredding. Document 
|                            |                       | still ongoing.                             | authorised destruction.
__________________________________________________________________________________________________________________________________
|**2. HR / employee records**| **3 years** for       | **Verified:** BCEA s31 requires specified  | Secure deletion for electronic
|— employment records,       |records covered by BCEA| employment records to be kept for **3**    | records and secure shredding
| remuneration, working hours|s31; **5 years for     | **years from the date of the last entry**  | for physical records once the 
| and related employee       |applicable SARS        | Applicable SARS employer/payroll tax       | applicable retention period 
| documentation              |employer/payroll tax   | records are subject to a **5-year**        | has expired and no legal hold
|                            |records. **Where two** | retention requirement. **UIF-specific**    | or other lawful retention
|                            |**periods apply to**   | **retention period requires**              | requirement applies.
|                            |**the same record,**   | **verification before being stated as a**  |
|                            |**the longer period**  | **number.**                                |
|                            |**governs.** **UIF-**  |                                            |
|                            |**specific retention** |                                            |
|                            |**period needs**       |                                            |
|                            |**verification.**      |                                            |
__________________________________________________________________________________________________________________________________
|**3. Customer loyalty-**    |**24 months** after the| **No specific statutory period verified.** | Secure digital deletion or
|**programme data** — names, |customer's last loyalty| Proposed business period under s14(1)(b),  | appropriate de-identification.
| email addresses, loyalty   |activity, unless an    | justified by the purpose of administering  | Remove unnecessary copies and
| points, account information|active account or other| the loyalty programme and avoiding         | address applicable backups/
|                            |documented purpose     | unnecessary retention.                     | replicas through the deletion 
|                            |justifies continued    |                                            | process. 
|                            |retention. **Pending** |                                            |    
|                            |**Owner approval.**    |                                            |
__________________________________________________________________________________________________________________________________
|**4. POS transaction and**  |**24 months for**      | No specific statutory period verified for  | Secure digital deletion after
|**operational records** -   |**operational records**| ordinary operational POS records. Proposed | the applicable period.
|sales transactions,         |forming part of        | business period under **POPIA s14(1)(b)**  | Preserve records subject
|transaction history,        |financial/tax          | based on operational reporting,            | to an authorised legal
|receipts, reconciliation    |documentation follow   | reconciliation,customer queries and        | hold or ongoing investigation.
|reporting data. **Excludes**|the applicable         | historical transaction support.            |
|**all access,**             |**5-year requirement** |                                            |   
|**authentication and**      |**Pending Owner**      |                                            |
|**security audit logs.**    |**approval for the**   |                                            |
|                            |**operational period** |                                            |
__________________________________________________________________________________________________________________________________
|**5. CCTV footage** —       | **30 days, then**     |**No specific statutory period verified.**  | Automated secure overwriting/
| recordings from areas such |**automatic overwrite**| Proposed business period under s14(1)(b),  | deletion. If footage is
| as entrances, tills and    | unless an incident/   | based on the cafe's security purpose and   | required for an incident or
| customer areas             | legal hold applies.   | the need to investigate incidents reported | investigation, isolate and
|                            | **Pending Owner**     | within a reasonable period.                | preserve the relevant
|                            | **approval**          |                                            | recording with restricted
|                            |                       |                                            | access and an audit trail. 
__________________________________________________________________________________________________________________________________
|**6. Customer/business**    |**24 months after**    | **No universal statutory period verified** | Secure deletion according to 
|**email records** — emails  |**closure of the**     | **for ordinary operational email.**        | the email-retention policy. 
| containing customer or     |**business/customer**  |Proposed business period under **s14(1)(b)**| Apply legal holds where
| business information       |**matter,** unless the | based on operational reference and dispute | necessary.
|                            |email forms part of a  | resolution needs.                          |
|                            |record subject to a    |                                            |
|                            |longer legal/business  |                                            |
|                            |retention requirement. |                                            |
|                            |**Pending Owner**      |                                            |
|                            |**approval**           |                                            |
__________________________________________________________________________________________________________________________________
|**7. POS access and**       |**12 months**, unless  | **No specific statutory period verified**  | Secure deletion after the
|security audit logs- user   |an incident,           | **for POS access/security logs.            | approved logging period;
|login/logout events,        |investigation or       | Proposed business period under **POPIA**   | preserve relevant logs for 
|authentication attempts,    |compliance requirement | **s14(1)(b),** based on security           | investigations, incidents 
|privilege changes, access   |requires longer        | monitoring, incident investigation and     | or legal proceedings.
|events and audit-trail      |retention. **Pending** | accountability requirements.               |     
|records. Google Drive/      |**Owner approval.**    |                                            |   
|vendor access and other     |                       |                                            |
|audit logs. **Excludes**    |                       |                                            |
|**transaction/sales**.      |                       |                                            |

## A Restriction Scenario
The cafe should restrict the processing of the disputed loyalty transaction while the customer's claim is being investigated. The specific record should be retained, but it should be flagged or placed under a processing restriction so that it is not altered, relied upon for further loyalty processing, or used for unrelated purposes until the cafe verifies its accuracy and determines how the dispute should be resolved.

The record should not be deleted because it may be necessary to establish what actually happened and to resolve the dispute. At the same time, it should not continue to be processed as normal because its accuracy has been challenged. Once the investigation is complete, the cafe can either correct the record if the customer is right, confirm it if the record is accurate, or take another appropriate action based on the findings.

## Secure Disposal Procedure
**Fresh Brew Cafe — Secure Disposal of Expired Records**

1. **Identify records due for disposal**
   Review the retention schedule and identify records whose approved retention period has expired, including POS exports, expired backups, printed receipts and signed forms.

2. **Confirm that disposal is authorised**
   Before destruction, verify that the record is not subject to a legal requirement, audit, investigation, dispute, legal hold, or other valid reason for continued retention.

3. **Obtain disposal approval**
   An authorised manager or designated responsible person must approve the disposal and confirm the records being destroyed.

4. **Secure digital records**
   Delete expired POS exports and other digital records using an appropriate secure-deletion method. Where storage media are being retired or disposed of, use appropriate media sanitisation or physical destruction so that the information cannot reasonably be reconstructed.

5. **Address backups and copies**
   Identify relevant copies in backups, shared drives, exports and other storage locations. Remove them according to the café's approved backup and retention process rather than assuming that deleting the primary copy is sufficient.

6. **Secure physical records**
   Place expired printed receipts, signed forms and other personal-information records in a secure disposal container. Do not place them in ordinary rubbish or recycling.

7. **Destroy physical records securely**
   Use cross-cut shredding, pulping, or an appropriately secure destruction service so that the original information cannot be reconstructed into an intelligible form.

8. **Verify destruction**
   Confirm that the records have been securely destroyed or deleted and that no unauthorised readable copies remain under the cafe's control.

9. **Record the disposal**
   Maintain a disposal log showing the record category, date, retention period, disposal method, person authorising disposal, and date of completion.

10. **Escalate exceptions**
    If there is uncertainty about whether a record may be destroyed, **do not destroy it**. Place it on hold and escalate the matter to the responsible manager/Information Officer for verification.
