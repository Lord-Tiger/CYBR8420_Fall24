------------------------------
**Part 1 - Use & Misuse Cases**
------------------------------ 
------------------------------
**Use Case #1**
------------------------------

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/d4175490b8aeb6879d2d3da248f0d5f73c762f8d/Media/Admin_Use_%26_Misuse_Cases2.jpg)

**Actors:**
-	System Admin / Engineer (User)
-	Wizard Spider (Misuser)

**Use Case:**
-	Managing & Making System Changes

**Misuse Case:**
-	Exploiting System Vulnerabilities
-	Hide Tracks / Using VPN / Tor
-	IP Spoofing

**Assessment:**

In this use case where the Admin/Engineer manages the system, he uses the admin dashboard/page to make system changes. The bad actor, in this case, Wizard Spider, a cybercriminal organization, tries to exploit the system’s vulnerabilities through code execution and trying to gain elevated privileges. Regular audits, system updates, logging and monitoring are in place to prevent this misuse of the system.
The attacker then tries to hide their tracks to circumvent these measures, using VPN and other venues like Tor. The system is configured to prevent connections from unpermitted IP addresses using access lists. The attackers attempt to use IP spoofing to gain access to the system from the allowed IP ranges, the attackers got that information from public IP records pages, like Arin. The system is, however, protected with digital signing, only machines with verified certificates can make admin connections, there are also packet inspection measures via the local firewall.

------------------------------
**Use Case #2**
------------------------------
![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/20512fe81c29bfc15c40ed0c0b58a4d9c77ff405/Media/Doctor.jpg)

**Actors:**
-	Doctor (User)
-	Scott (Misuser)

**Use Case:**
-	Doctor Communication/Emails

**Misuse Case:**
-	Phishing Email
-	Virus Implementation
-	Man in the Middle Listening

**Assessment:**

This case is highly important because many of the cyber threats are focused on the users. Patient care requires communication across the entire hospital campus.  The first thing is to update policies and educate the doctors on phishing emails. They are the first wall of defense and must be aware of these scams. This is not a perfect solution since users will eventually click on a phishing email therefore IT must make sure that all patches and updates are applied to the firewall and Firewall and Intrusion Detection Systems to detect and prevent any viruses. To further prevent man in the middle (MITM) or eavesdropping it is apparent to make sure that all communication is encrypted to further prevent the access to sensitive information.  

------------------------------
**Use Case #3**
------------------------------
![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/b0cfb6caa9eac17a59085e884ff55cab67be9a7d/Media/Untitled%20Diagram.jpg)

-----------------
**Part 2 - OSS**
-----------------

There was a recent patch OpenEMR 7.02 that caused multiple issues. Some of these issues included are: dashboard unable to load for patients, a bug that allows scripts to run forever, and affecting the pdf creators for reports that could affect patient reports and slow down care. We would make sure to test updates on local machines prior to pushing the update out to the public. With this update the social security number of patients are visibly logged. This would violate many laws such as HIPPA and PII and would require immediate attention. I would update the permissions that allows only certain individuals with the rights to access these logs.
