------------------------------
**Part 1 - Use & Misuse Cases**
------------------------------ 
------------------------------
**Use Case #1**
------------------------------

**Actors:**
-	System Admin / Engineer (User)
-	Wizard Spider (Misuser)

**Use Case:**
-	Managing & Making System Changes

**Misuse Case:**
-	Exploiting System Vulnerabilities
-	Hide Tracks / Using VPN / Tor
-	IP Spoofing

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/d4175490b8aeb6879d2d3da248f0d5f73c762f8d/Media/Admin_Use_%26_Misuse_Cases2.jpg)

**Assessment:**

In this use case where the Admin/Engineer manages the system, he uses the admin dashboard/page to make system changes. The bad actor, in this case, Wizard Spider, a cybercriminal organization, tries to exploit the system’s vulnerabilities through code execution and trying to gain elevated privileges. Regular audits, system updates, logging and monitoring are in place to prevent this misuse of the system.
The attacker then tries to hide their tracks to circumvent these measures, using VPN and other venues like Tor. The system is configured to prevent connections from unpermitted IP addresses using access lists. The attackers attempt to use IP spoofing to gain access to the system from the allowed IP ranges, the attackers got that information from public IP records pages, like Arin. The system is, however, protected with digital signing, only machines with verified certificates can make admin connections, there are also packet inspection measures via the local firewall.

------------------------------
**Use Case #2**
------------------------------

**Actors:**
-	Doctor (User)
-	Scott (Misuser)

**Use Case:**
-	Doctor Communication/Emails

**Misuse Case:**
-	Phishing Email
-	Virus Implementation
-	Man in the Middle Listening

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/20512fe81c29bfc15c40ed0c0b58a4d9c77ff405/Media/Doctor.jpg)

**Assessment:**

This case is highly important because many of the cyber threats are focused on the users. Patient care requires communication across the entire hospital campus.  The first thing is to update policies and educate the doctors on phishing emails. They are the first wall of defense and must be aware of these scams. This is not a perfect solution since users will eventually click on a phishing email therefore IT must make sure that all patches and updates are applied to the firewall and Firewall and Intrusion Detection Systems to detect and prevent any viruses. To further prevent man in the middle (MITM) or eavesdropping it is apparent to make sure that all communication is encrypted to further prevent the access to sensitive information.  

------------------------------
**Use Case #3**
------------------------------

**Actors:**
-	Clinician (User)
-	Rogue Clinician (Misuser)

**Use Case:**
-	Patient Record Creation

**Misuse Case:**
-	Fake Patient Records
-	Prescriptions

**Diagram:**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/b0cfb6caa9eac17a59085e884ff55cab67be9a7d/Media/Untitled%20Diagram.jpg)

**Assessment:**

In this misuse scenario, a rogue clinician attempts to exploit the OpenEMR system to create fake patient records and issue fraudulent prescriptions for controlled substances. The clinician’s goal is to use these false prescriptions to pick up the medication at a pharmacy, bypassing the system’s safeguards. However, several security measures are implemented to mitigate this risk:

Multi-Factor Authentication (MFA) for Patient Identity Verification:

The system enforces MFA during the creation of new patient records, requiring a secondary verification step to validate the patient's identity. This adds an additional layer of security, making it harder for the clinician to add unauthorized patients. However, the rogue clinician circumvents this control by using a compromised or unauthorized device to bypass the MFA check.
Role-Based Access Control (RBAC):

The RBAC configuration restricts clinicians from both creating and approving patient records, separating these duties to minimize misuse. The rogue clinician is unable to complete both tasks because the RBAC policies enforce strict access controls, ensuring that the same clinician cannot act as both the creator and the verifier of new patients.
Data Loss Prevention (DLP):

A DLP system is in place to monitor for suspicious activities, such as unusual patterns in patient record creation. If a clinician tries to create multiple new patient profiles rapidly or if records exhibit characteristics typical of fraudulent entries (e.g., incomplete information or irregular demographics), the DLP triggers alerts for further investigation. This control helps detect and flag fake patient records before they can be used to generate prescriptions.
Secure Configuration and Hardening:

Secure configuration and hardening practices are applied across the OpenEMR system to ensure that all security settings are correctly implemented and maintained. This includes limiting access to sensitive configuration files, disabling unused functionalities, and applying security patches regularly. These measures reduce the attack surface and help prevent exploitation of system vulnerabilities.
Outcome and Mitigation
Although the rogue clinician attempts to circumvent the MFA control using a rogue device, the RBAC policy effectively prevents the misuse by ensuring that record creation and approval are separated. Additionally, the DLP and secure system configurations provide further barriers, ensuring that even if a fake patient record is created, it is flagged before any fraudulent prescriptions can be issued and picked up. This layered security approach illustrates how combining multiple preventive methods can mitigate insider threats and reduce the likelihood of successful misuse.


-----------------
**Team Reflection**
-----------------
This assignment has been the most challenging we have undertaken in this class so far. Our initial difficulty was grasping the core problem we needed to address. We were overthinking when it came to the deliverables. In our first attempt at building a misuse case, we mistakenly used multiple actors, use and misuse cases in a single diagram, when a simpler approach would have been more appropriate. After consulting with our professor, we gained some direction; however, there was still some ambiguity for me personally (Abdoul). Despite this, we managed to develop three misuse cases and requested each team member to create a diagram and upload it to our GitHub repository for review and feedback from the rest of the group.

**Individual Contributions:**

Abdoul: Did case #3 including the diagram and the case's assesment, he did the team's reflection and made updates to the overall document.

Brian: Did case #3 including the diagram and the case's assesment, contributed to the OSS project documentation section and explained to the team during a meeting the assignment and deliverables, helped with the document.

Yasir: Did case #1 including the diagram and the case's assesment, created a GitHub projects page to track the overall project tasks and milestones over time. Created the assignment's md document, helped convert it to the proper format, contributed to the reflection and the OSS project documentation section as well as overall review and fixes to the document.

----------------------------------------------
**Part 2 - OSS Project Documentation Review**
----------------------------------------------

OpenEMR has dedicated pages on how to secure the software, hardening it and a HIPPA security assessment write up for compliance.

- [Securing OpenEMR](https://www.open-emr.org/wiki/index.php/Securing_OpenEMR)
- [Security Assesment](https://www.open-emr.org/wiki/index.php/Security_Assessment)

These guides provides essential steps and best practices for securing an OpenEMR installation to protect sensitive patient medical and billing data in order to comply with government regulations such as HIPAA. Key areas covered by these guides include the following:

- Web Server Security
- Database Security
- File Permissions and Ownership
- User Authentication
- Network Security
- Regular Updates and Patches
- Backup Strategy
- HIPPA Compliance

It does seem like there's need to be more technical details to make the recommendations more actionable, for example, including common troubleshooting tips for issues that may arise while securing OpenEMR. In addition, the network part, which is critical, only features basic guidance on this area. It would be good to offer guidelines for setting up a Web Application Firewall (WAF) for instance, or specific software tools that integrate with OpenEMR for monitoring and application threat prevention. OpenEMR is PHP and web-based for a lot of its functions, being publicly available for patients and the public, application-specific protection setup is an important piece.

On another note concerning security issues, there was a recent patch OpenEMR 7.02 that caused multiple issues. Some of these issues included are: dashboard unable to load for patients, a bug that allows scripts to run forever, and affecting the pdf creators for reports that could affect patient reports and slow down care. We would make sure to test updates on local machines prior to pushing the update out to the public. With this update the social security number of patients are visibly logged. This would violate many laws such as HIPPA and PII and would require immediate attention. I would update the permissions that allows only certain individuals with the rights to access these logs.

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
