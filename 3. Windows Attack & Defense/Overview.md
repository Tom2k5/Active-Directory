# Introduction
The following is a complete list of all attacks described in this module:

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
# Lab Environment
The attacks will be executed from the provided Windows 10 (WS001) and Kali Linux machines. The assumption is that an attacker has already gained remote code execution (of some sort) on that Windows 10 (WS001) machine. The user, which we assume is compromised, is `Bob`, a regular user in Active Directory with no special permissions assigned.

The environment consists of the following machines and their corresponding IP addresses:

- `DC1`: `172.16.18.3` (depending on the section)
- `DC2`: `172.16.18.4` (depending on the section)
- `Server01`: `172.16.18.10` (depending on the section)
- `PKI`: `172.16.18.15` (depending on the section)
- `WS001`: `DHCP or 172.16.18.25` (depending on the section)
- `Kali Linux`: `DHCP or 172.16.18.20` (depending on the section)

