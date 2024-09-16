*Project Proposal - Team 6*

*OpenEMR Seucurity Features*
OpenEMR is built with a variety of security features designed to protect patient data, ensure privacy, and comply with regulations like HIPAA (Health Insurance Portability and Accountability Act). Here are some of those features:

1. User Authentication and Access Controls
  •	Role-Based Access so that access is assigned based on roles, for example, patient, doctor, admin etc.
  •	Authentication, a secure login mechanism using usernames and passwords
  •	Two-Factor/Multi-Factor Authentication, the application allows for the use of 2FA/MFA to be used in addition to conventional usernames and passwords, such as       tokens and push notifications.
  •	User Lockouts that allows the system admin to configure it so accounts are locked out after a specific number of failed login attempts.
  •	OAuth2 and JWT Authentication for API calls.
2. Data Encryption
  •	Data-at-Rest, data stored on the servers including billing, medical and personal records.
  •	Data-in-Transit, the application supports HTTPS (SSL/TLS) to encrypt traffic as it traverses the network.
3. Auditing & Logging
  •	Audit logs that show all access and changes to patient records, allowing administrators to track who accessed or modified data.
  •	Activity logs that tracks various actions, including user logins, record creation, editing, and deletion.
  •	Reporting capabilities that allow admins to generate reports based on audit logs in order to ensure compliance and to investigate potential breaches.
4. Compliance with HIPPA & Other Regulations
  •	OpenEMR features a guide that can be used to harden the application in order to reach compliance with HIPPA, it’s also, by design, made to meet the stringent       requirements of HIPAA and other regulations to ensure the security and privacy of protected health information (PHI). It’s worth noting that while this may         apply to the software itself, the system, network and other services that interact with the application have to be hardened themselves in order to reach total      compliance.
  •	Can achieve “ONC Certified” status with the purchase of a third party service module.
5. Database & System Security
  •	Database access controls for database-level security so that access is limited only to authorized users.
  •	Data integrity checks to ensure the data is accurate and has not been tampered with.
6. Backup & Recovery
  •	OpenEMR supports automated, regular backups that can be used to restore operations in case of loss due to a compromise or a disaster.
  •	Encrypted Backups.
7. File Access & Permissions
  •	Limited access to files, documents and media based on roles and permissions (read, write and so on).
8. Threat Protection
  •	Firewall integration, including network firewalls and WAFs (Web Application Firewalls) for the publicly facing portals.
  •	Intrusion Detection Systems can be used to protect the OpenEMR environment.
  •	Antivirus software.
9. Secure Communications
  •	Encrypted Messaging.
  •	Secure Email Support.
10. Updates & Patch Management
  •	Regular security updates.
  •	Automatic Patching.
