------------------------------
**Use Case #1**
------------------------------
Actors:
-	System Admin / Engineer (User)
-	Wizard Spider (Misuser)

Use Case:
-	Managing & Making System Changes

Misuse Case:
-	Exploiting System Vulnerabilities
-	Hide Tracks / Using VPN / Tor
-	IP Spoofing

Assessment:
In this use case where the Admin/Engineer manages the system, he uses the admin dashboard/page to make system changes. The bad actor, in this case, Wizard Spider, a cybercriminal organization, tries to exploit the system’s vulnerabilities through code execution and trying to gain elevated privileges. Regular audits, system updates, logging and monitoring are in place to prevent this misuse of the system.
The attacker then tries to hide their tracks to circumvent these measures, using VPN and other venues like Tor. The system is configured to prevent connections from unpermitted IP addresses using access lists. The attackers attempt to use IP spoofing to gain access to the system from the allowed IP ranges, the attackers got that information from public IP records pages, like Arin. The system is, however, protected with digital signing, only machines with verified certificates can make admin connections, there are also packet inspection measures via the local firewall.
