------------------------------
**Part 1: Assurance Cases & Assesments**
------------------------------
------------------------------
**Assurance Case #1 - OpenEMR Minimizes Disclosure of Patient Data**
------------------------------

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/60d576355c1975abef388a08915b9a51d3761a69/Media/Assurance_Case1_Minimizes_Data_Disclosure.jpg)

**Assesment:** 

In this assurance, the first claim, also the top claim, is that OpenEMR minimizes the disclosure of patients’ medical and billing data. For context, OpenEMR is an open-source software that is used in a healthcare environment to manage healthcare records.
The first rebuttal (R1) tries to argue against the top claim by bringing up the possibility of communications/traffic interception.
Sub-Claim (C2) states that OpenEMR encrypts data during transmission and at rest in storage (when configured correctly).

Three rebuttal arguments question this claim, the first one (R2) is by presenting the possibility of the software being misconfigured, the second one (R3) brings up third-party integrations being configured in a way that bypasses these safeguards, and the third (R4) mentions the possible presence of software vulnerabilities. Sub-claim (C3) counters (R2), with configurations being peer reviewed and the implementation of automated configurations standards compliance, this is backed by evidence (E1), with configurations and software documentation showing the use of AES-256 Encryption as well evidence (E2) for having configuration audits showing such compliance. The same evidence (E2) is also used to support sub-claim (C4) that mentions OpenEMR’s utilization of strong access controls and IPSec tunnels for integrations. Sub-claim (C5) counters rebuttal (R4) with the fact that automated software security patches are downloaded and applied as soon as they’re released, and vulnerabilities scans are run regularly. This claim is backed by evidence (E4) and (E5) as the software system logs and the software version page would show latest security patches having been applied as well as the presence of periodic vulnerability scan reports.

Undermine (UM1) questions evidence (E2), stating that these reports could have been doctored/modified or made internally to show favorable results and compliance.
Sub-claim (C6) counters that by stating that the reports in question are certified, not manipulated with the evidence (E3) being external audits and independent pen testing reports that cannot be internally modified.
For Inference Rule (IR1), if the software implements adequate security and privacy controls, then it minimizes the disclosure of patient data, this statement is undercut (UC1) with the possibility of the software not being updated/supported any longer, this statement is then countered with the claim that the OpenEMR software is an open-source software with an active community of developers and has been developed and maintained for over 20 years.

------------------------------------
**Assurance Case #2 - OpenEMR's Billing & Insurance Modules Minimize Unauthorized Access**
------------------------------------

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/main/Media/Assurance%20Case-password.jpg)

**Assesment:** 

This claim is focused on the billing and insurance modules of OpenEMR and how they minimize unauthorized access to the accounts (C1). The context is based on the patients having access to the billing software to pay for medical care. Patients need to be able to access this software from any device to set up payments of their accounts.  The rule is that a new patient is identified when creating a new account. This can be undercut by different person creates the account. This can be prevented by identifying the patient by state issued ID when creating the account.

The first rebuttal (R1) to the prevention of unauthorized access is if the login information is obtained to access the account. By implementing regular password changes (C2) and apply this by policy then this will help prevent it (E1). Another subclaim to this rebuttal R1 is the claim of the addition of Multi Factor Authentication (C3) that will limit the ability to access the account even if the log in information is obtained. IF there is no secondary device R3 to use MFA than email authentication (C5) can be sent to the same device. This is support by the MFA Policy and reviews (E2). Another rebuttal to MFA (C3) is the inability of user to understand MFA (R4) due to the addition of new technology. There is education and training by staff (C6) that can be found in Free online support chat or forum (E3).

The second main rebuttal to unauthorized access is Password is susceptible to brute force attacks (R2). This is something that cyber professionals need to be aware of. By implementing strong password policies (C4) we can minimize the threat. Dictionary attacks for the password (R5) could then bypass the strong password policies. By limiting the number of log in attempts (C7) this can limit the threat. This is supported by CAPTCHA (E4) for verification and security questions for Identity Authentication (E5). 

------------------------------------
**Assurance Case #3 -**
------------------------------------

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/9c6b16b96e2743ae27c2a1798a1d146844a8a3ee/Media/Assurance%20case%20(1).jpg)

**Assesment:**
Top-Level Claim

Claim: "OpenEMR ensures that only authorized users can access the system, and patient actions are based on their roles."
This is a high-level, comprehensive claim that sets the foundation for security. It focuses on ensuring proper access control and role-based permissions, which are critical for protecting sensitive medical data.

Supporting Argument Structure
Sub-claims are supporting the main top-level claim with specific security mechanisms (such as RBAC, multi-factor authentication (MFA), and session control).

Rebuttals: The diagram incorporates counterarguments such as "RBAC may not be well-defined" or "MFA can be bypassed" to enhance credibility by acknowledging potential weaknesses.
Sub-Claim for Audits: An essential element of this diagram is the emphasis on auditing and oversight. This indicates a dynamic and monitored system, which helps to assure stakeholders that even if RBAC or MFA is bypassed, there are safety nets in place.

Sub-Claims and Rebuttals

Sub-Claim C1: Discusses unauthorized access to patient records, with a rebuttal addressing the flexibility of RBAC. It shows that while RBAC limits access, potential misconfigurations need constant oversight.

Sub-Claim C3: Provides an argument for MFA, with an effective rebuttal acknowledging that session management could be a vulnerability, and that even MFA can be bypassed if not implemented securely.

Sub-Claim C4: Addresses the potential risks around RBAC misconfiguration or insufficient oversight.

Evidence Support

Evidence 1: Configuration logs and settings for session expiration events to back up the sub-claim on RBAC.

Evidence 2: Descriptions and logs showing MFA implementations, adding credibility to the security claims around authentication.

Evidence 3: Audit definitions and records verifying that RBAC is correctly implemented and actively managed.

Each evidence node is specific and provides clear, actionable proof to support the claims.

------------------------------
**Part 2: Alignments With the Actual OSS Project**
------------------------------
The Assurance cases here present a few pieces of evidence, some of which are available within the software itself, others can be added or be applied using integrations with other software or hardware components, as discussed below.

**AES-256 Encryption:**

OpenEMR supports encryption for data in transit and data at rest, it uses strong encryption standards, such as AES-256 for that purpose, securing sensitive data like patient information as it’s stored and when retrieved. OpenEMR also uses SSL/TLS for its communications. You can enable these encryption settings through the administration settings (Administration -> Globals).

**Configuration Auditing:**

OpenEMR features robust auditing features that can track configuration changes. This functionality includes logging events for things like patient record creation, updates as well as deletions, along with other administrative tasks like account lockouts and security configuration changes.

**Software Logs:**

The OSS project provides extensive logging capabilities including the ability to capture different types of events such as database queries, system changes, and logins and logouts. The logs are also important for compliance.

**External Audits & Periodic Vulnerability Scans:**

The part would be handled by various tools and software that is not necessarily related or integrated into OpenEMR, for instance, if Qualys, a third-party security software might be used by an independent cyber security firm to pen test the software itself and the infrastructure it’s built on, by checking for open ports or the validity of the certificate and encryption used on the public webpages. These reports are generated automatically by the solution and obtained by the engineer. Those conducted by the external firms are also verified and then handed to the responsible engineer.

**Policies and reports:**

OpenEMR site has the policies and procedures posted. The Password Policy Enhancements policy includes strong passwords implementation and password change every 3 months. There are plicies that layout the existence of CAPTCHA for human authentication and the number of login attempts that are allowed to access an account. 

**Free online forum and chat:**

There are forums that have previous questions that have been discussed along with the ability to post questions to help with your issues. There are multiple support chats that allow you to speak to OpenEMR contributors to assist with any issues you may have.

**Multi-Factor Authentication:**

There is an instructions manual on how to complete the Multi-factor Authentication setup. This is not automatically built into the user access, but an option that a user can set up. It is a step by step guide on how to set MFA up and where to receive the authentication token.

**Session Timeout Configuration:**

OpenEMR allows administrators to configure session timeout settings, specifying how long a session can remain idle before the user is automatically logged out. This setting is customizable based on the organization’s security requirements.

**Automatic Logout and Notifications:**

When a session is about to expire due to inactivity, OpenEMR may provide notifications to the user warning them that their session is about to end, giving them a chance to stay logged in. If the user does not respond, the system automatically logs them out to prevent unauthorized access

--------------------------
**Team Reflections:**
--------------------------
For this project, we held a meeting on Discord last Wednesday to brainstorm various assurance cases. During the session, each of us identified and suggested potential approaches, and we came up with different options. After discussing them, we each selected one to develop further in preparation for our meeting with the professor on Thursday.

During the call with the professor, we received valuable feedback and began refining our project accordingly. Our first assurance case focuses on the confidentiality of patient data, the second ensures that users have access to the software based on their designated roles, and the third addresses preventing unauthorized access to billing and insurance information.

This time we also made sure that our issues in GitHub are closed and project milestones are up to date with the project events.

On Sunday we met over Discord to decide our direction for the assignment and to peer review our drafts, we convened for another call for a few hours as a team on Monday, we collabrated and put all of our works together for the final submission of the assignment. It's understandable that we all have jobs and families outside class, but we still have to improve on our communications and have more collabration sessions over Disord for upcoming team assignments.

-------------------------------------
**Team Individual Contributions:**
-------------------------------------
**Yasir:** Did assurance case #1 including the diagram and the case's assessment, updated the GitHub projects page and closed all open issues. Created the assignment's md document, helped convert it to the proper format, contributed to the reflections and references sections as well as part #2 of the assignment (Alignments) that are relevant to case #1 such as AES-256 encryption, configuration auditing, software logs and external Audits and periodic vulnerability scans pieces. Also did an overall review and fixed issues in the deliverable document.

**Brian:** Did assurance case #2 including the diagram and the case's asessment, contributed to the reference and part #2 of the assignemnt (MFA, Free online forum and chat, Policies and Procedures). Assisted witht the completeion of the assurance cases  and review of the document.

**Abdoul:** For this project, I developed the top-level claim: "OpenEMR ensures that only authorized users can access the system and perform actions based on their roles." I also contributed to the team's reflection process, assisted in reviewing the other cases, and actively participated in brainstorming the assurance cases we needed to focus on for this task.

-------------------------------------
**Link to the team's project board:**
-------------------------------------
<https://github.com/users/Lord-Tiger/projects/3>
-------------------------------------------------------
**Reference Links:**
-------------------------------------------------------
<https://github.com/openemr/openemr>

<https://www.open-emr.org/wiki/index.php/Security_Assessment>

<https://www.open-emr.org/wiki/index.php/Securing_OpenEMR>

<https://github.com/openemr/openemr/blob/master/CONTRIBUTING.md>

<https://github.com/openemr/openemr?tab=readme-ov-file>

<https://www.securityweek.com/vulnerabilities-in-openemr-healthcare-software-expose-patient-data/>

<https://community.open-emr.org/c/security/17>

<https://www.open-emr.org/chat/>

<https://www.open-emr.org/wiki/index.php/1._Password_policy_enhancements#:~:text=If%20the%20entered%20password%20is,not%20a%20letter%20or%20number).>

<https://github.com/openemr/openemr/blob/master/src/Common/Session/SessionTracker.php>
