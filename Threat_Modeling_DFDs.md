------------------------------
**Part 1: Threat Modeling**
------------------------------
------------------------------
**Data Flow Diagram (DFD) - User Data Access & Authentication**

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/d193c44768d4787a9852f7c027ac8667a7b4faab/DFD/User_Access_DFD.png)

[User Data Access & Authentication Threat Modeling Report](https://htmlpreview.github.io/?https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/ea7b1096221866ec648467e8942c35e04f561ab3/DFD/User_Access_ThreatModelingReport.htm)

------------------------------
**Part 2: Observations**
------------------------------

The threat modeling tool’s automated analysis mode identified 55 threats based on the user access and authentication flow diagram we created, only 14 of these threats are relevant to OpenEMR and its scope of operation. Here are some of the relevant threats that were found based on their categories.

**Repudiation:**
The threat of repudiation is mitigated through the use of system and user activity logs.

**Tampering:**
The threat of tampering with the data is limited since only authorized accounts are allowed to make data changes.

**Elevation Of Privilege:**
This threat can be mitigated if MFA is used, MFA is an ad-on module that can be added to the setup but is not standard, this can be a little bit of a gap since MFA is still not as widely used as it should be, if it were to be a standard part of the setup, it would be more likely to be implemented because it’s well-known that standard usernames/passwords on their own can be vulnerable to impersonation and possibly gaining access to accounts with elevated privileges.
This threat can also come from various exploitations of vulnerabilities that could possibly be present in the code through the use of injection attacks and Cross-site request forgery (CSRF or XSRF). OpenEMR utilizes PHP and is a web-based application with exposure to the internet for patient records and so on, which makes it susceptible for web application attacks such as SQL injections and Cross-Site Scripting (XSS), and these were vulnerabilities identified in the past, as recently as last year but have since been fixed. OpenEMR features input validations to mitigate these types of attacks.

**Denial Of Service:**
Trying to overwhelm the system with login requests can be mitigated as the software allows you to limit the number of failed login attempts. Other parts of the setup may require redundancy or load balancing in place, but those parts are not relevant to the software codebase.

**Spoofing:**
Publicly accessible pages are open. The patient portal and medical staff access are protected with various authentication methods, standard and MFA. In addition, some sensitive data can only be accessed internally.

**Information Disclosure:**
With the potential of unintended data disclosure, MFA tokens are generated locally from within the module or the cloud plugin, these tokens cannot be reused, they also expire and multiple attempts are limited as well.

The threat modeling tool itself is pretty helpful, but it could feel a bit dated since modern software is dependent on many moving parts that it may not be able to automatically identify. Today, you don’t normally have a web application hanging on the internet on its own, there are always multiple layers of security involved, including those outside the codebase, such as web application firewalls (WAF) that can conduct input validations and prevent injection attacks for instance. Such solutions can fill some gaps not in the original code, such as geo blocking. That’s not to say that the software code itself is not secure enough, on the contrary, it seems like the community developers are doing a great job addressing all security issues as they arise for OpenEMR.


------------------------------
**Team Reflection**
------------------------------
For this phase of our project, we focused on building a Data Flow Diagram (DFD) for our use case. We held a meeting with our professor to seek guidance, and it was decided that we would concentrate on the authentication component, as it encompasses many of the system's processes. Following the meeting, we developed the initial DFD and reconvened on Sunday to further refine and expand it.

The primary takeaway from this activity has been recognizing the value of threat modeling software. It highlighted potential security issues we had not previously considered, prompting us to conduct a deeper analysis to categorize and determine the relevance of various threats. Additionally, we needed to research historical and current issues or gaps within the software to understand how similar vulnerabilities have been addressed in the past.

In summary, this activity has encouraged us to proactively consider security flaws during the design process and leverage the threat modeling tool to uncover additional vulnerabilities, ultimately strengthening the system’s overall security.

-------------------------------------------------------
**Reference Links:**
-------------------------------------------------------
<https://github.com/openemr/openemr>

<https://www.open-emr.org/wiki/index.php/Security_Assessment>

<https://www.open-emr.org/wiki/index.php/Securing_OpenEMR>

<https://github.com/openemr/openemr/blob/master/CONTRIBUTING.md>

<https://www.securityweek.com/vulnerabilities-in-openemr-healthcare-software-expose-patient-data/>

<https://community.open-emr.org/c/security/17>

<https://www.open-emr.org/wiki/index.php/1._Password_policy_enhancements#:~:text=If%20the%20entered%20password%20is,not%20a%20letter%20or%20number).>

