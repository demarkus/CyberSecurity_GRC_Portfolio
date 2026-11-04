# Personal Information Impact Assessment: Facial-Recognition Loyalty Proposal

*Fresh Brew Café (simulated organisation) · Author: Mark Yeboah Opoku*

> A full POPIA PIIA concluding 'Do Not Proceed as Designed' on necessity and proportionality grounds.

## Phases 1 & 2: Scoping and Description
# Fresh Brew Cafe
# Personal Information Impact Assessment (PIIA)
# Facial-Recognition CCTV / Loyalty Programme Proposal
_______________________________________________________

**Document status:** Draft — Pre-implementation
**Assessment stage:** Phases 1 & 2 — Scoping and Description
**Responsible Party:** Fresh Brew Cafe
**PIIA Owner:** Information Officer
**Business Owner:** Cafe Owner
**Date:** 1 September 2026
**Decision status:** **Not approved for implementation pending completion of the full PIIA**

# Phase 1 — Initiation and Scoping

# 1.1 Initiative being assessed

Fresh Brew Cafe proposes introducing a **facial-recognition capability integrated with CCTV and its customer loyalty programme**.

The intended business purpose is to allow customers who **voluntarily enrol** to be recognised automatically and linked to their loyalty account so that points, rewards, or account identification can occur without requiring a physical loyalty card or manual account lookup.

The proposal potentially involves cameras capturing the faces of **all persons within the camera's field of view**, including customers who have **not enrolled** in the loyalty programme. This distinction is material to the privacy assessment.

# 1.2 Purpose of this PIIA

This PIIA assesses whether the proposed processing:

* is necessary and proportionate to the stated loyalty purpose;
* complies with POPIA's conditions for lawful processing;
* creates risks to customers, employees, visitors, or other data subjects;
* requires additional technical, organisational, contractual, or privacy controls; and
* should be approved, modified, or rejected before deployment.

# 1.3 PIIA trigger assessment

|**Trigger                         | Status              | Assessment**
__________________________________________________________________________________________________________________________________
| **Biometric information**        | **Confirmed**       | Facial-recognition templates used to identify individuals constitute
|                                  |                     | biometric information and therefore involve **special personal**
|                                  |                     | **information** under POPIA.
__________________________________________________________________________________________________________________________________
| **Systematic monitoring**        | **Confirmed**       | CCTV cameras may repeatedly capture individuals entering or moving 
|                                  |                     | through monitored cafe areas. 
__________________________________________________________________________________________________________________________________
                                                                       
| **Automated identification**     | **Confirmed**       | Facial characteristics would be compared automatically against 
|                                  |                     | enrolled loyalty profiles. 
__________________________________________________________________________________________________________________________________
| **New / intrusive technology**   | **Confirmed**       | Facial recognition is materially more intrusive than a conventional 
|                                  |                     | loyalty card, QR code, email address, or phone-number lookup.
__________________________________________________________________________________________________________________________________
| **Linking of datasets**          | **Confirmed**       | A facial identity may be linked with loyalty membership, visits, 
|                                  |                     | transactions, points, and purchase history.
__________________________________________________________________________________________________________________________________
| **Potential profiling**          | **Possible**        | Visit frequency and purchase history could create behavioural profiles
|                                  |                     | if the system permits such analysis. This is **not approved as part** 
|                                  |                     | **of the stated purpose**.     
__________________________________________________________________________________________________________________________________
| **Processing of non-members**    | **Confirmed risk**  | CCTV may capture people who have never enrolled. Their images must not
|                                  |                     | become permanent biometric profiles merely because they entered the 
|                                  |                     | cafe.                        
__________________________________________________________________________________________________________________________________
| **Children's information**       | **Possible / not**  | Children may enter the cafe. Enrolment rules and treatment of minors
|                                  | **yet established** | must be defined before implementation. 
__________________________________________________________________________________________________________________________________
| **Large-scale processing**       | **Not established** | Fresh Brew Cafe is a small business and no evidence currently 
|                                  |                     | establishes large-scale processing. 
__________________________________________________________________________________________________________________________________
| **Cross-border processing**      | **To be confirmed** | Depends on the location of any facial-recognition vendor's servers, 
|                                  |                     | support personnel, backups, or subprocessors. 
__________________________________________________________________________________________________________________________________
| **Vendor / Operator processing** | **Likely**          | If an external provider hosts, analyses, or stores facial data on
|                                  |                     | behalf of the cafe, it would likely act as an Operator, subject to the
|                                  |                     | final contractual arrangement. 

# Phase 1 conclusion

The proposal triggers a **high level of privacy concern** because it combines biometric information, CCTV monitoring, automated identification, dataset linkage, and possible third-party processing.

A full PIIA is therefore required before implementation.

# Phase 2 — Description of the Processing

# 2.1 Data subjects

The proposed processing may affect:

1. **Enrolled loyalty customers**
2. **Non-enrolled customers**
3. **Employees**
4. **Suppliers and contractors**
5. **Visitors**
6. **Children accompanying customers**

Only voluntarily enrolled customers are intended to receive facial-recognition loyalty functionality.

# 2.2 Personal information to be processed

# A. Enrolment information

For a customer who chooses facial recognition:

* customer name;
* loyalty-account identifier;
* email address and/or phone number where already required for the loyalty account;
* enrolment date;
* consent/authorisation record;
* facial image captured during enrolment;
* biometric facial template derived from the image.

The enrolment photograph should **not be retained merely because it was used to generate the template** unless a specific operational need is demonstrated and approved.

# B. CCTV / recognition information

Cameras may process:

* live facial images;
* CCTV video;
* date and time;
* camera/location identifier;
* temporary facial characteristics or mathematical representations generated for matching;
* match/no-match result;
* confidence score, where generated by the system.

For individuals who are **not enrolled**, any temporary biometric representation created solely to determine whether a match exists must be **discarded immediately after the comparison** and must not be added to a persistent facial database.

# C. Loyalty information linked after a successful match

Where an enrolled customer is recognised, the system may retrieve:

* loyalty-account number;
* points balance;
* rewards eligibility;
* transaction date/time;
* purchases linked to the loyalty account;
* reward redemption history.

Facial recognition must **not automatically authorise payment or financial transactions** merely because a facial match occurs.

# D. Administrative and audit data

The system may also generate:

* enrolment and withdrawal records;
* administrator access logs;
* facial-template creation/deletion logs;
* matching-system logs;
* system errors;
* security-event logs;
* vendor support logs where applicable.

# 2.3 Processing flow

The proposed processing is:

**1. Enrolment**

Customer voluntarily joins facial-recognition loyalty functionality.

↓

**2. Facial capture**

A facial image is captured for enrolment.

↓

**3. Template generation**

Software converts relevant facial characteristics into a biometric template.

↓

**4. Account association**

The template is linked to the customer's loyalty identifier.

↓

**5. Subsequent CCTV capture**

A participating customer appears before an enabled camera.

↓

**6. Temporary comparison**

The system extracts facial characteristics from the live image and compares them against authorised enrolled templates.

↓

**7. Match**

If sufficiently matched, the appropriate loyalty account is returned to the POS.

↓

**8. Loyalty activity**

Points or rewards are associated with the account.

↓

**9. Logging**

The system records only the information necessary for security, audit, and loyalty-account administration.

A failed or non-member match must **not result in creation of a new biometric profile**.

# 2.4 Purpose of processing

The approved proposed purpose is:

> **To identify customers who have voluntarily enrolled in Fresh Brew Cafe's facial-recognition loyalty programme so that their loyalty account can be retrieved and loyalty benefits applied conveniently at the point of service.**

# 2.5 Access to personal information

Access must follow least privilege.

|**Role                         | Permitted Access**
__________________________________________________________________________________________________________________________________
| **Cashier / Barista**         | Loyalty match confirmation, loyalty identifier, points/rewards necessary to serve the customer
__________________________________________________________________________________________________________________________________
| **Cashier / Barista**         | **No access to biometric templates or bulk CCTV exports**
__________________________________________________________________________________________________________________________________
| **Shift Manager**             | Limited account troubleshooting and approved operational records 
__________________________________________________________________________________________________________________________________
| **Owner**                     | Authorised administrative oversight 
__________________________________________________________________________________________________________________________________
| **Information Officer**       | Privacy compliance, complaints, data-subject requests, PIIA oversight and audit evidence 
__________________________________________________________________________________________________________________________________
| **IT Contractor**             | Technical access only where required for maintenance or incident response; access must be 
|                               | authorised and logged 
__________________________________________________________________________________________________________________________________
| **Facial-recognition vendor** | Only the data technically necessary to provide the contracted service 
__________________________________________________________________________________________________________________________________
| **Other customers/public**    | No access 

**Bulk export of biometric templates must be technically restricted.**

Administrative access should require **strong authentication and MFA**.

# 2.6 Vendor / Operator processing

# Current status

**Vendor: Not yet selected / contractual terms not yet reviewed.**

Therefore the PIIA must not assume that vendor processing is safe or compliant.

Before approval, Fresh Brew Cafe must establish:

* whether facial images leave the cafe premises;
* whether biometric templates are processed locally or in the cloud;
* vendor hosting locations;
* countries from which support personnel may access the service;
* subprocessors used;
* encryption in transit and at rest;
* administrator-access controls;
* retention periods;
* deletion capability;
* backup retention;
* incident-notification process;
* whether the vendor uses customer data for analytics or AI/model training;
* whether the vendor shares information with other entities.

# POPIA relationship

Where a vendor processes the information **solely on Fresh Brew Cafe's behalf and under its instructions**:

* **Fresh Brew Cafe:** Responsible Party
* **Facial-recognition provider:** Operator

A written Operator agreement must therefore address confidentiality and appropriate security safeguards.

If the vendor intends to determine its **own independent purposes** for the facial information, that requires separate legal analysis and cannot simply be treated as ordinary Operator processing.

# 2.7 Storage and location

**Current status: Not yet established.**

The final architecture must specify whether biometric data is stored:

* on the local POS or recognition appliance;
* on a cafe server;
* in a South African cloud environment;
* outside South Africa;
* simultaneously in multiple environments;
* in vendor backups.

This is a **PIIA approval blocker** until documented.

# 2.8 Data sharing

Under the proposed scope, personal information should be shared only with:

* Fresh Brew Cafe personnel with a defined business need;
* the contracted facial-recognition Operator where technically necessary;
* authorised IT support personnel where necessary;
* authorities or other recipients where disclosure is legally required.

The cafe does **not approve** sale of biometric information, advertising disclosure, unrelated analytics, or vendor reuse for model training.

# 2.9 Phase 2 finding

**Assessment:** ⚠️ **Processing defined in principle, but material design gaps remain.**

The cafe can now identify:

* the proposed purpose;
* categories of data;
* affected data subjects;
* expected processing flow;
* permitted access;
* intended retention approach; and
* likely Responsible Party/Operator relationship.

However, the following remain unresolved:

1. vendor selection;
2. hosting location;
3. cross-border processing;
4. subprocessors;
5. technical deletion capability;
6. treatment of children;
7. final CCTV coverage and whether recognition is continuous or point-of-service only;
8. formally approved retention periods;
9. proof that non-member biometric representations are immediately discarded;
10. confirmation that vendor data will not be reused for AI/model training.

# Phase 1 & 2 decision

> **Proceed to Phase 3 risk assessment, but do not approve deployment.**

**Conclusion**: The proposal is sufficiently described to begin assessing privacy risks, but **not sufficiently resolved to go live**.

The most important issue for the next phase will be whether **facial recognition is genuinely necessary and proportionate for something as low-risk as earning café loyalty points**, even if every technical security control works perfectly.

## Phase 3: Risk, Necessity/Proportionality, and Mitigation
# Fresh Brew Cafe
# Personal Information Impact Assessment (PIIA)
# Facial-Recognition CCTV / Loyalty Programme Proposal

**Phase 3 — Risk, Necessity/Proportionality, and Mitigation**

# 3.1 Risks to Data Subjects

The assessment must focus not only on harm to Fresh Brew Cafe, but on how the processing could affect the **rights, freedoms, dignity, privacy, and interests of the people being scanned or identified**.

|**Risk to Data Subject   | Potential Impact                                            | Likelihood | Impact     | Initial Risk**
__________________________________________________________________________________________________________________________________
|**1. Unwanted biometric**| Customers, employees, children, or visitors may be scanned  | High       | High       | **High**
|**surveillance**         | even though they never joined the loyalty programme.        |            |            |
|                         | Individuals may feel monitored or lose control over how     |            |            |
|                         | their face is processed.                                    |            |            |
__________________________________________________________________________________________________________________________________
|**2. Misidentification/**| The system may incorrectly identify one person as another,  | Medium     | Medium–High| **High**
|**false match**          | resulting in incorrect loyalty activity, disclosure of      |            |            |
|                         | another customer's account information, embarrassment, or   |            |            |
|                         | unfair treatment.                                           |            |            |
__________________________________________________________________________________________________________________________________
|**3. Biometric data**   | If facial templates are stolen or improperly disclosed, the | Medium      | High       | **High** 
|**compromise**          | individual cannot simply replace their face like a password.|             |            |
|                        | This creates potentially long-lived privacy and identity    |             |            |
|                        | risks.                                                      |             |            |
__________________________________________________________________________________________________________________________________
|**4. Function creep/**  | Data originally collected for loyalty identification could  | Medium      | High       | **High**
|**profiling**           | later be used to track visit frequency, purchasing          |             |            |
|                        | behaviour, employee activity, demographics, marketing, or   |             |            |
|                        | other purposes the customer did not expect.                 |             |            |
__________________________________________________________________________________________________________________________________
|**5. Loss of genuine**  | Customers may feel they must submit to facial recognition   | Medium      | Medium     | **Medium**
|**choice**              | to receive the same loyalty benefits as other customers,    |             |            |
|                        | making consent less meaningful.                             |             |            |
_________________________________________________________________________________________________________________________________
|**6. Vendor misuse or** | A facial-recognition provider could retain templates, use  | Medium       | High       | **High**
|**secondary use**       | data to improve its models, combine it with other datasets,|              |            |
|                        | or transfer it through subprocessors without customers     |              |            |
|                        | understanding the extent of processing.                    |              |            |
__________________________________________________________________________________________________________________________________
|**7. Excessive**        | Facial images, templates, CCTV footage or recognition logs | Medium       | High       | **High** 
|**retention**           | could be retained longer than necessary, increasing        |              |            |
|                        | exposure and allowing historical tracking of individuals.  |              |            |

These risks are materially different from ordinary cybersecurity risks such as “the cafe may suffer downtime.” They concern **what may happen to the individual because their personal information is being processed**.

# 3.2 Necessity Test

# Stated purpose

The stated purpose is:

> **Recognise returning loyalty customers so that their loyalty account can be retrieved and rewards applied conveniently.**

The key necessity question is:

> **Is facial recognition genuinely necessary to achieve that purpose?**

### Assessment: **No**

Facial recognition is **not necessary** to recognise a returning loyalty customer.

Fresh Brew Cafe can achieve essentially the same outcome using significantly less intrusive methods, including:

* a loyalty QR code in a mobile wallet;
* customer phone-number lookup;
* email-based loyalty account lookup;
* a physical or digital loyalty card;
* a customer-generated PIN;
* scanning a loyalty-app barcode.

All of these can identify the loyalty account **without processing immutable biometric information or continuously analysing faces through CCTV**.

POPIA's minimality principle requires personal information to be adequate, relevant and **not excessive** for the processing purpose. 

# Necessity finding

**Result: FAILED**

> Facial recognition is convenient, but convenience is not the same as necessity.

The loyalty purpose can be accomplished effectively using less intrusive information.

# 3.3 Proportionality Test

The proportionality question is:

> **Even if facial recognition provides some benefit, is the privacy intrusion proportionate to that benefit?**

# Benefits identified

Potential benefits include:

* faster loyalty-account retrieval;
* reduced need for physical loyalty cards;
* potentially smoother customer experience;
* reduced manual lookup by staff.

# Privacy intrusion

To obtain those relatively modest benefits, the system would:

* process biometric information;
* potentially scan everyone entering the camera's field of view;
* create persistent facial templates for enrolled customers;
* potentially link identity with transaction and visit history;
* introduce false-match risk;
* introduce long-lived consequences from biometric compromise;
* potentially involve a third-party facial-recognition provider.

# Assessment: **Disproportionate for the stated purpose**

The business benefit is **convenience in administering loyalty points**, whereas the privacy cost involves highly intrusive biometric identification.

That imbalance is significant.

> **A facial-recognition system might be technically impressive, but the privacy intrusion is difficult to justify merely to make buying coffee and earning loyalty points slightly more convenient.**

# Proportionality finding

**Result: FAILED in its current form**

# 3.4 Preferred Mitigation — Change the Design

The strongest mitigation is not stronger encryption.

It is:

> **Do not use facial recognition for this purpose.**

Fresh Brew Cafe should instead implement a less intrusive loyalty identification method, preferably:

**QR/barcode loyalty identification**, supported by phone-number or email lookup as a fallback.

This approach achieves the same business objective while eliminating most biometric risks entirely.

# Resulting risk reduction

| **Risk                     | Facial recognition | QR / loyalty-card alternative**         |
| -------------------------- | -----------------: | --------------------------------------: |
| Biometric compromise       | High               | **Eliminated**                          |
| Non-member facial scanning | High               | **Eliminated**                          |
| Facial misidentification   | Medium/High        | **Eliminated**                          |
| Biometric vendor misuse    | High               | **Eliminated**                          |
| Behavioural profiling      | Possible           | Still possible, but easier to control   |
| Data breach                | Still possible     | Remains, but impact substantially lower |

This is an example of **privacy by design**: eliminate unnecessary processing instead of trying to secure unnecessary processing.

# 3.5 If Management Chooses to Proceed Anyway

If the Owner decides there is a compelling business case to continue evaluating facial recognition despite the failed necessity/proportionality assessment, the following should be treated as **minimum preconditions**, not optional enhancements.

# A. Voluntary opt-in only

* Facial recognition must be strictly **opt-in**.
* No customer should lose loyalty benefits for refusing.
* A non-biometric alternative must provide equivalent rewards.
* Withdrawal must be simple.

# B. No persistent processing of non-members

The system must be designed so that faces of non-enrolled persons:

* are not enrolled;
* are not retained as biometric templates;
* are not placed on watchlists;
* are not used for analytics;
* are discarded immediately after any temporary comparison.

# C. Point-of-service recognition only

Do **not** deploy continuous recognition across the cafe.

Recognition should occur only where necessary, for example at a designated POS recognition point activated during the loyalty transaction.

This materially reduces surveillance.

# D. Data minimisation

Store only:

* the minimum biometric template required for matching;
* the loyalty identifier;
* necessary audit information.

Do not retain the original enrolment photograph once template creation is complete unless a documented necessity exists.

# E. Strict purpose limitation

Contractually and technically prohibit:

* advertising profiling;
* emotion recognition;
* demographic inference;
* employee monitoring;
* unrelated customer tracking;
* AI/model training;
* sale or reuse of biometric data.

# F. Short retention and automatic deletion

Implement automatic deletion when:

* the customer withdraws;
* the loyalty account closes;
* the approved inactivity period expires.

Deletion must cover production systems and follow a documented backup-expiry process.

# G. Strong access controls

Require:

* MFA for administrators;
* role-based access;
* no cashier access to biometric templates;
* logging of administrative access;
* periodic access reviews;
* immediate revocation during off-boarding.

# H. Vendor controls

Before contracting with a facial-recognition provider:

* complete vendor due diligence;
* document the Operator relationship;
* prohibit secondary use;
* prohibit model training using café data;
* identify subprocessors;
* confirm hosting jurisdictions;
* require encryption;
* require deletion capability;
* require incident notification;
* provide audit/evidence rights.

# I. Accuracy and false-match controls

The cafe must:

* test accuracy before deployment;
* establish an appropriate match threshold;
* require human confirmation before revealing account details;
* never use facial recognition alone to approve payment;
* provide a process to challenge incorrect identification.

# J. Transparency

Prominent notices should tell people:

* facial recognition is in use;
* what it does;
* what information is processed;
* whether participation is optional;
* who receives the information;
* retention periods;
* how to withdraw;
* how to exercise POPIA rights.

# 3.6 Residual Risk Assessment

Even if all proposed mitigations are implemented, several risks cannot be fully eliminated:

| Residual risk                               | Remaining level |
| ------------------------------------------- | --------------- |
| Biometric information compromised           | **Medium**      |
| False recognition                           | **Low–Medium**  |
| Function creep                              | **Low–Medium**  |
| Vendor misuse                               | **Low–Medium**  |
| Customer discomfort / surveillance concerns | **Medium**      |
| Excess processing relative to purpose       | **Medium–High** |

The most important residual issue is that technical controls **do not solve the necessity problem**.

A perfectly encrypted, perfectly access-controlled biometric database may still be an **unnecessary biometric database**.

# 3.7 Phase 3 Decision

# Privacy assessment

**Necessity:** ❌ **Not demonstrated**
**Proportionality:** ❌ **Not demonstrated**
**Less intrusive alternative available:** ✅ **Yes**
**Risk can be materially reduced through alternative design:** ✅ **Yes**

# Recommendation

> **Do not approve the proposed CCTV/facial-recognition loyalty system in its current form.**

Fresh Brew Cafe should implement a **QR code, digital loyalty card, phone-number lookup, or similar non-biometric mechanism** instead.

If management nevertheless wishes to proceed, implementation should remain **blocked** until the legal basis for processing special personal information, vendor architecture, retention, non-member treatment, consent/choice design, technical safeguards, and all Phase 3 mitigation actions have been formally resolved and approved.

**PIIA conclusion:**

> **The question is not merely whether Fresh Brew Cafe *can secure* facial recognition. The more fundamental question is whether it needs facial recognition at all. For a loyalty programme, the current answer is no.**

## Phase 4: Documentation, Sign-off, and a Recommendation
# Fresh Brew Café
# Personal Information Impact Assessment (PIIA)
# Facial-Recognition CCTV / Loyalty Programme Proposal

**Phase 4 — Documentation, Sign-off, and Recommendation**

# 4.1 Final Recommendation

# Decision: **Do Not Proceed as Designed**

Based on the findings from Phases 1–3, the proposed facial-recognition CCTV/loyalty system should **not be approved in its current form**.

The reason is not that the proposal cannot be secured technically. The more fundamental problem is that the processing is **not necessary or proportionate to the stated business purpose**.

The stated purpose is to:

> recognise returning loyalty customers so that their loyalty account can be retrieved and rewards applied conveniently.

That objective can be achieved effectively through substantially less intrusive methods, including:

* QR-code or barcode loyalty identification;
* a digital or physical loyalty card;
* phone-number or email lookup; or
* a customer PIN.

The proposed system would instead introduce biometric processing, repeated facial identification, possible processing of non-members, vendor dependency, false-match risk, and potentially long-lived consequences if biometric information were compromised.

# Recommended course of action

> **Fresh Brew Cafe should abandon the facial-recognition element and implement a non-biometric loyalty-identification method instead.**

This achieves the business objective while materially reducing privacy risk.

# 4.2 Alternative Management Decision

If management believes there is a compelling reason to continue exploring facial recognition, the appropriate decision would be:

# **Proceed with changes — but do not deploy yet**

Deployment must remain blocked until, at minimum:

1. facial recognition is strictly voluntary and opt-in;
2. customers receive equivalent loyalty benefits without using biometrics;
3. recognition is limited to a designated point-of-service interaction rather than continuous cafe-wide identification;
4. non-enrolled faces are not persistently stored or profiled;
5. biometric retention and automatic deletion rules are technically enforced;
6. the facial-recognition vendor and all subprocessors are identified and assessed;
7. hosting locations and any cross-border processing are documented;
8. vendor use of cafe data for AI/model training or unrelated purposes is contractually prohibited;
9. strong access controls, MFA, logging and encryption are implemented;
10. false-match thresholds and human verification controls are tested;
11. privacy notices and withdrawal mechanisms are implemented;
12. the lawful basis and conditions for processing biometric/special personal information are formally confirmed; and
13. the remaining residual risks are formally accepted by authorised management.

Completion of these controls would require an **updated PIIA before deployment**.

# 4.3 Sign-off Requirements

The following roles should review and sign the final assessment:

|**Role                                     | Responsibility                               | Required Action**
------------------------------------------: |---------------------------------------------:|--------------------------------------
| **Information Officer**                   | POPIA oversight and PIIA accountability      | **Approve/reject privacy assessment**
|                                           |                                              | **and confirm required actions** 
_________________________________________________________________________________________________________________________________
| **Cafe Owner**                            | Business accountability and risk acceptance  | **Approve the business decision**
|                                           |                                              | **and any accepted residual risk**  
_________________________________________________________________________________________________________________________________
| **IT Contractor / Technical Lead**        | Technical design and safeguards              | Confirm architecture, security 
|                                           |                                              | controls, deletion capability and
|                                           |                                              | technical feasibility
__________________________________________________________________________________________________________________________________
| **Loyalty / Operations Owner**            | Business purpose and operational requirement | Confirm whether the business need 
|                                           |                                              | can be met by less intrusive 
|                                           |                                              | alternatives
__________________________________________________________________________________________________________________________________
| **Vendor representative, where selected** | Operator processing                          | Provide evidence on architecture,
|                                           |                                              | security, subprocessors, retention
|                                           |                                              | and deletion arrangements 

Where specialist legal interpretation is required, particularly regarding biometric processing or contractual terms, the Information Officer should obtain appropriate legal advice before implementation.

# Important governance rule

The **IT Contractor should not be the person who accepts the privacy risk**.

Technical personnel can confirm whether controls work, but accountability for accepting residual privacy risk belongs with the appropriate business owner and Information Officer.

# 4.4 Sign-off Record

| Role                | Name       | Decision                                         | Signature  | Date       |
| ------------------- | ---------- | ------------------------------------------------ | ---------- | ---------- |
| Information Officer | __________ | ☐ Approve ☐ Reject ☐ Conditional                 | __________ | __________ |
| Café Owner          | __________ | ☐ Approve ☐ Reject ☐ Conditional                 | __________ | __________ |
| IT Contractor       | __________ | ☐ Technical controls confirmed ☐ Gaps remain     | __________ | __________ |
| Operations Owner    | __________ | ☐ Business need confirmed ☐ Alternative selected | __________ | __________ |

# Final decision

**Recommended:** ☒ **Do Not Proceed as Designed**

☐ Proceed as Designed
☐ Proceed with Conditions
☒ Do Not Proceed as Designed

**Preferred alternative:** Non-biometric loyalty identification.

# 4.5 PIIA Review Requirements

This PIIA must not be treated as a one-time document.

# Mandatory review points

The assessment should be reviewed:

* **before any implementation or pilot** of facial recognition;
* whenever the **purpose of processing changes**;
* when a facial-recognition **vendor or subprocessor changes**;
* when new categories of personal information are collected;
* if processing expands to additional cameras, locations or customer groups;
* if children or other higher-risk groups become involved;
* where information is transferred to a new jurisdiction;
* after a material privacy or security incident;
* when a significant control failure occurs;
* when legal or regulatory requirements affecting the processing change.

# Periodic review

If facial recognition were ever approved and implemented, Fresh Brew Cafe should perform a **formal PIIA review at least annually**, with earlier reassessment whenever there is a material change.

If the recommendation is followed and a conventional QR/card-based loyalty system is implemented instead, the cafe should record that decision and reassess the replacement processing if its scope later changes materially.

# 4.6 Outstanding Actions

| Action                                                            | Owner                   | Status   |
| ----------------------------------------------------------------- | ----------------------- | -------- |
| Select non-biometric loyalty alternative                          | Cafe Owner / Operations | **Open** |
| Document revised data flow                                        | Information Officer     | **Open** |
| Define retention schedule for loyalty information                 | Information Officer     | **Open** |
| Update customer privacy notice                                    | Information Officer     | **Open** |
| Confirm access controls for loyalty system                        | IT Contractor           | **Open** |
| Close facial-recognition proposal or document management override | Cafe Owner              | **Open** |

# 4.7 Final PIIA Conclusion

The proposed facial-recognition loyalty initiative introduces significant privacy risks because it would process biometric information for a purpose that can be achieved through substantially less intrusive means.

The assessment found:

* **PIIA triggers:** multiple and significant;
* **security risk:** potentially manageable with strong controls;
* **necessity:** **not demonstrated**;
* **proportionality:** **not demonstrated**;
* **less intrusive alternative:** **readily available**;
* **recommended decision:** **Do Not Proceed as Designed**.

> **Final recommendation: Reject the facial-recognition loyalty design and implement a non-biometric alternative.**
