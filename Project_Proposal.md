---------------------------------
**The Omaha Health Clinic**
---------------------------------
Omaha Health Clinic is a mid-sized, community-focused healthcare provider located in Omaha Nebraska. It serves a diverse population of approximately 25,000 patients annually. The clinic offers a broad range of healthcare services including general practice, pediatrics, family medicine, mental health services as well as specialist consultations. Omaha Health is committed to providing high-quality care with a “Patient Wellness First!” objective. The clinic prioritizes wellness, accessibility and efficient service delivery.

In order to streamline our medical operations and improve efficiency, accessibility and for better patient care, we have fully integrated a digital medical records system into our day-to-day functions. For this we have selected OpenEMR as our medical software of choice, and with the transition to EMR, Omaha Health has transitioned from outdated paper-based records to a more efficient, modern, digital record keeping approach, enabling doctors, nurses, and administrative staff to access critical patient data instantly from any secure device within the clinic's network, while also allowing the patients themselves to access their own medical and billing records remotely through a dedicated patient portal.


-------------------------
**Software Description**
-------------------------
According to the decription provided on OpenEMR's website, The community of behind the project is committed to maintaining OpenEMR as a free, open-source software solution for medical practices, the platform enjoys robust support from both users and developers. With over 4,000 downloads per month and contributions from more than 200 developers and companies, OpenEMR is the most widely used free electronic medical records system today. Its codebase is continuously improved through open collaboration, and the software is available in more than 30 languages, making it a truly global solution for healthcare providers.

-----------------------------------
**System Engineering View Diagram**
-----------------------------------
![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/main/Media/OpenEMR_SystemsEngineeringView.jpg)

------------------------------
**Perceived Security Threats**
------------------------------
Users of OpenEMR, an open-source electronic medical records (EMR) and practice management system, typically face a range of threats typical for healthcare digital environments. These threats often relate to the sensitive nature of healthcare data and the operational context of healthcare delivery. Here are some of the key threats:

**Data Security & Privacy Threats:** From malware and ransomware attacks to insider threats and data loss due to breaches and disasters.

**Compliance & Regulatory Risks:** For example, HIPAA Violations in the US and GDPR Non-Compliance in Europe, if security compliance was not well practiced.

**System Vulnerabilities:** Affecting OpenEMR’s code itself, if no patch is released in a timely manner and/or if said vulnerabilities remain unpatched by the medical clinic. This threat can also come from third-party plugins or modules integrated with OpenEMR.

**Operational & Performance Threats:** Due to downtime and service disruptions, usually unplanned, especially those caused by server, software, or a network connectivity issue at the clinic. There can also be integration challenges when it comes to integrating OpenEMR with other healthcare systems, such as those used by external labs, insurance or pharmacy systems, possibly leading to data mismanagement or synchronization issues.

**User-Related Threats:** Brought forth due to misconfigurations or accidental deletions. This can be to the data itself or server/network configurations. Also, the use of weak passwords or encryption algorithms. Users can also be subject to social engineering attacks such Phishing attacks due to lack of awareness and/or training.

**Remote Access Security:** With the rise of telehealth and remote access, the use of weak remote access protocols can result in data exposure or data loss if proper, strong encryption and authentication protocols are not in place. If personal devices are allowed, unsecure, unmanaged devices used by staff accessing OpenEMR remotely may expose the system to cyber threats.

**Lack of dedicated support:** OpenEMR being an open-source solution, often depends on community support, which may not always be reliable or timely. This could result in delayed responses during critical system failures or attacks.

-----------------------------
**OpenEMR Security Features**
-----------------------------
OpenEMR is built with a variety of security features designed to protect patient data, ensure privacy, and comply with regulations like HIPAA (Health Insurance Portability and Accountability Act). Here are some of those features:

1\. User Authentication and Access Controls

- Role-Based Access so that access is assigned based on roles, for example, patient, doctor, admin etc.
- Authentication, a secure login mechanism using usernames and passwords.
- Two-Factor/Multi-Factor Authentication, the application allows for the use of 2FA/MFA to be used in addition to conventional usernames and passwords, such as tokens and push notifications.
- User Lockouts that allows the system admin to configure it so accounts are locked out after a specific number of failed login attempts.
- OAuth2 and JWT Authentication for API calls.

2\. Data Encryption

- Data-at-Rest, data stored on the servers including billing, medical and personal records.
- Data-in-Transit, the application supports HTTPS (SSL/TLS) to encrypt traffic as it traverses the network.

3\. Auditing & Logging

- Audit logs that show all access and changes to patient records, allowing administrators to track who accessed or modified data.
- Activity logs that tracks various actions, including user logins, record creation, editing, and deletion.
- Reporting capabilities that allow admins to generate reports based on audit logs in order to ensure compliance and to investigate potential breaches.

4\. Compliance with HIPPA & Other Regulations

- OpenEMR features a guide that can be used to harden the application in order to achieve compliance with HIPPA, it’s also, by design, made to meet the stringent requirements of HIPAA and other regulations to ensure the security and privacy of protected health information (PHI). It’s worth noting that while this may apply to the software code itself, the system, network and other services that interact with the application have to be hardened themselves in order to reach total compliance.
- Can achieve “ONC Certified” status with the purchase of a third party service module.

5\. Database & System Security

- Database access controls for database-level security so that access is limited only to authorized users.
- Data integrity checks to ensure the data is accurate and has not been tampered with.

6\. Backup & Recovery

- OpenEMR supports automated, regular backups that can be used to restore operations in case of loss due to a compromise or a disaster.
- Encrypted Backups.

7\. File Access & Permissions

- Limited access to files, documents and media based on roles and permissions (read, write and so on).

8\. Threat Protection

- Firewall integration, including network firewalls and WAFs (Web Application Firewalls) for the publicly facing portals.
- Intrusion Detection Systems can be used to protect the OpenEMR environment.
- Antivirus software.

9\. Secure Communications

- Encrypted Messaging.
- Secure Email Support.

10\. Updates & Patch Management

- Regular security updates.
- Automatic Patching.

-------------------------------------------------------
**A Brief Summary of Security-Related OpenEMR History**
-------------------------------------------------------
OpenEMR has experienced various security challenges over the years, including critical vulnerabilities like RCE, SQL injection, and XSS. One recent example is a vulnerability discovered in 2023 that allowed remote attackers to steal sensitive information or execute arbitrary commands to take over the OpenEMR systems which has since been fixed. The platform has responded quickly with patches for that incident and others over the years and through various security feature improvements, and the adoption of modern best practices like 2FA, RBAC, and HTTPS. The open-source nature of the project ensures continuous audits, and the platform's commitment to improving its security posture remains strong.

-----------------------
**Project Motivation**
-----------------------
For this project, we focused on the healthcare sector due to one of our team members' professional experience in the field, which we believed would bring valuable insights. We selected OpenEMR as our subject, as it is a globally recognized open-source healthcare software, used by institutions such as the Peace Corps. OpenEMR is fully functional, allowing patients to schedule appointments, manage payments, and access their prescriptions and lab results.

Healthcare providers can use the platform to view appointments, order lab tests, prescribe medication, and receive clinical decision support.
Additionally, we chose this project because it is a multi-user platform that faces various security threats and challenges, making it a compelling subject for our analysis.

--------------
**Team work**
--------------
After the team was formed, we initially faced challenges with communication. However, we resolved this by setting up a Discord server and creating a GitHub repository as required for the class. While one team member is still missing, we are moving forward with the project using the resources we have.

Throughout the process, we held two meetings, during which we divided the project tasks relatively equally, leveraging each team member’s strengths.
We plan to hold one final meeting to consolidate our work before the submission.

-------------------------------------------------------
**Reference Links:**
-------------------------------------------------------
<https://github.com/openemr/openemr>

<https://www.open-emr.org/wiki/index.php/Security_Assessment>

<https://www.open-emr.org/wiki/index.php/Securing_OpenEMR>

<https://github.com/openemr/openemr/blob/master/CONTRIBUTING.md>

<https://github.com/openemr/openemr?tab=readme-ov-file>

<https://www.securityweek.com/vulnerabilities-in-openemr-healthcare-software-expose-patient-data/>
