------------------------------
**Part 1:**
------------------------------
------------------------------
**Assurance Case #1 - OpenEMR Minimizes Disclosure of Patient Data**
------------------------------


![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/main/Media/Assurance_Case1_Minimizes_Data_Disclosure.jpg)

**Assesment:** 

Affecting OpenEMR’s code itself, if no patch is released in a timely manner and/or if said vulnerabilities remain unpatched by the medical clinic. This threat can also come from third-party plugins or modules integrated with OpenEMR.
In this assurance, the first claim, also the top claim, is that OpenEMR minimizes the disclosure of patients’ medical and billing data. For context, OpenEMR is an open-source software that is used in a healthcare environment to manage healthcare records.
The first rebuttal (R1) tries to argue against the top claim by bringing up the possibility of communications/traffic interception.
Sub-Claim (C2) states that OpenEMR encrypts data during transmission and at rest in storage (when configured correctly).

Three rebuttal arguments question this claim, the first one (R2) is by presenting the possibility of the software being misconfigured, the second one (R3) brings up third-party integrations being configured in a way that bypasses these safeguards, and the third (R4) mentions the possible presence of software vulnerabilities. Sub-claim C3 counters R2, with configurations being peer reviewed and the implementation of automated configurations standards compliance, this is backed by evidence (E1), with configurations and software documentation showing the use of AES 256 Encryption as well evidence (E2) for having configuration audits showing such compliance. The same evidence (E2) is also used to support sub-claim (C4) that mentions OpenEMR’s utilization of strong access controls and IPSec tunnels for integrations. Sub-claim (C5) counters rebuttal (R4) with the fact that automated software security patches are downloaded and applied as soon as they’re released, and vulnerabilities scans are run regularly. This claim is backed by evidence (E4) and (E5) as the software system logs and the software version page would show latest security patches having been applied as well as the presence of periodic vulnerability scan reports.

Undermine (UM1) questions evidence (E2), stating that these reports could have been doctored/modified or made internally to show favorable results and compliance.
Sub-claim C6 counters that by stating that the reports in question are certified, not manipulated with the evidence (E3) being external audits and independent pen testing reports that cannot be internally modified.
For Inference Rule (IR1), if the software implements adequate security and privacy controls, then it minimizes the disclosure of patient data, this statement is undercut (UC1) with the possibility of the software not being updated/supported any longer, this statement is then countered with the claim that the OpenEMR software is an open-source software with an active community of developers and has been developed and maintained for over 20 years.

------------------------------------
**Assurance Case #2 - OpenEMR's Billing & Insurance Modules Minimize Unauthorized Access**
------------------------------------


![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/main/Media/Assurance%20Case-password.jpg)

**Assesment:** 

This claim is focused on the billing and insurance modules of OpenEMR and how they minimize unauthorized access to the accounts (C1). The context is based on the patients having access to the billing software to pay for medical care. Patients need to be able to access this software from any device to set up payments of their accounts.  The rule is that a new patient is identified when creating a new account. This can be undercut by different person creates the account. This can be prevented by identifying the patient by state issued ID when creating the account.

The first rebuttal (R1) to the prevention of unauthorized access is if the login information is obtained to access the account. By implementing regular password changes (C2) and apply this by policy then this will help prevent it (E1). Another subclaim to this rebuttal R1 is the claim of the addition of Multi Factor Authentication (C3) that will limit the ability to access the account even if the log in information is obtained. IF there is no secondary device R3 to use MFA than email authentication (C5) can be sent to the same device. This is support by the MFA Policy and reviews (E2). Another rebuttal to MFA (C3) is the inability of user to understand MFA (R4) due to the addition of new technology. There is education and training by staff (C6) that can be found in Free online support chat or forum (E3).

The second main rebuttal to unauthorized access is Password is susceptible to brute force attacks (R2). This is something that cyber professionals need to be aware of. By implementing strong password policies (C4) we can minimize the threat. Dictionary attacks for the password (R5) could then bypass the strong password policies. By limiting the number of log in attempts (C7) this can limit the threat. This is supported by CAPTCHA (E4) for verification and security questions for Identity Authentication (E5). 

------------------------------------
**Assurance Case #3 -**
------------------------------------
**Assesment:**


------------------------------
**Part 2:**
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



**Team Reflections:**

For this project, we held a meeting on Discord last Wednesday to brainstorm various assurance cases. During the session, each of us used AI tools to help identify potential approaches, and we generated about six different options. After reviewing them, we each selected one to develop further in preparation for our meeting with the professor on Thursday.

During the call with the professor, we received valuable feedback and began refining our project accordingly. Our first assurance case focuses on the confidentiality of patient data, the second ensures that users have access to the software based on their designated roles, and the third addresses preventing unauthorized access to billing and insurance information.

**Team Individual Contributions:**
