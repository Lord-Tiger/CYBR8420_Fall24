-----------------------------------
**System Engineering View Diagram**
-----------------------------------
![image]()

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

-----------------------------
**OpenEMR Security Features**
-----------------------------
OpenEMR is built with a variety of security features designed to protect patient data, ensure privacy, and comply with regulations like HIPAA (Health Insurance Portability and Accountability Act). Here are some of those features:

1\. User Authentication and Access Controls

- Role-Based Access so that access is assigned based on roles, for example, patient, doctor, admin etc.
- Authentication, a secure login mechanism using usernames and passwords
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

- OpenEMR features a guide that can be used to harden the application in order to reach compliance with HIPPA, it’s also, by design, made to meet the stringent requirements of HIPAA and other regulations to ensure the security and privacy of protected health information (PHI). It’s worth noting that while this may apply to the software itself, the system, network and other services that interact with the application have to be hardened themselves in order to reach total compliance.
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
