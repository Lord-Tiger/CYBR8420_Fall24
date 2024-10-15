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

**Assesment:** 
