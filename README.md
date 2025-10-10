# Active Directory

**Active Directory Attack and Defend** is a hands-on project designed to simulate real-world attack and defense scenarios within a Windows enterprise environment. The project focuses on common Active Directory vulnerabilities, such as privilege escalation, lateral movement, and domain enumeration, while also implementing defensive techniques like monitoring, hardening, and detection. It aims to strengthen practical skills in both offensive and defensive operations, following the MITRE ATT&CK framework.

The following is a complete list of all attacks and counters described in this project:

**Leveraging Windows Event Logs:**
- Initial Access:
	- `Detecting Common User/Domain Recon.`
	- `Detecing Password Spraying.`
	- `Detecting Responder-like Attacks.`
- Domain Roasting:
	- `Kerberoasting`
	- `AS-REProasting`
- GPO Enumeration:
	- `GPP Passwords`
	- `Misconfigured GPO Permissions (or GPO-deployed files)`
	- `Credentials in Network Shares`
	- `Credentials in User Attributes`
- Pass The Credentials:
	- `Pass-The-Hash.`
	- `Pass-The-Ticket.`
	- `Overpass-The-Hash.`
- Rogue Tickets:
	- `Kerberos Golden Ticket`
	- `Kerberos Sliver Tickets`
- Kerberos Delegation:
	- `Kerberos Constrained Delegation attack`
	- `Kerberos Unconstrained Delegation attack`
- Coercing Attacks:
	- `Print Spooler & NTLM Relaying`
	- `Coercing attacks & Kerberos Unconstrained Delegation`
- Rogue Certificates:
	- `PKI Misconfigurations` - `ESC1`
	- `PKI Misconfigurations` - `ESC8` (`Coercing` + `Certificates`)
- ACLs  Attacks:
	- `Object ACLs`
- DCSync/DCShadow:
	- `DCSync`
	- `DCShadow`

**Leveraging Zeek Logs:**
- `Detecting RDP Bruteforce Attacks.`
- `Detecting Beaconing Malware.`
- `Nmap port scanning`
- `Kerberos Bruteforce Attack.`
- `Kerberoasting.`
- `Golden Tickets.`
- `Cobalt Strike's PSExec.`
- `Zero Logon.`
- `Data Exfiltration (HTTP)`
- `Data Exfiltration (DNS)`
- `Ransomware`

---
