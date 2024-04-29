3/22/24, 3:47 PM OS Credential Dumping: /etc/passwd and /etc/shadow, Sub-technique T1003.008 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1003/008/ 1/4Thank you to Tidal Cyber and SOC Prime for becoming ATT&CK's ﬁrst Benefactors. To join the cohort, or learn more about this program visit our
Benefactors page.3/22/24, 3:47 PM OS Credential Dumping: /etc/passwd and /etc/shadow, Sub-technique T1003.008 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1003/008/ 2/4Home>Techniques>Enterprise>OS Credential Dumping>/etc/passwd and /etc/shadow3/22/24, 3:47 PM OS Credential Dumping: /etc/passwd and /etc/shadow, Sub-technique T1003.008 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1003/008/ 3/4OS Credential Dumping: /etc/passwd and /etc/shadow
Procedure Examples
ID Name Description
S0349 LaZagne LaZagne can obtain credential information from /etc/shadow using the shadow.py module.
Mitigations
ID Mitigation Description
M1027 Password Policies Ensure that root accounts have complex, unique passwords across all systems on the network.
M1026 Privileged Account
ManagementFollow best practices in restricting access to privileged accounts to avoid hostile programs from
accessing such sensitive information.
Detection
ID Data SourceData Component Detects
DS0017 Command Command
ExecutionMonitor executed commands and arguments that may attempt to dump the contents of
/etc/passwd and /etc/shadow to enable oﬄine password cracking.
DS0022 File File Access Monitor for ﬁles being accessed that may attempt to dump the contents of /etc/passwd and
/etc/shadow to enable oﬄine password cracking. The AuditD monitoring tool, which ships
stock in many Linux distributions, can be used to watch for hostile processes attempting to
access /etc/passwd and /etc/shadow , alerting on the pid, process name, and arguments of
such programs.Adversaries may attempt to dump the contents of /etc/passwd and /etc/shadow to enable oﬄine password cracking. Most modern Linux
operating systems use a combination of /etc/passwd and /etc/shadow to store user account information including password hashes in
/etc/shadow . By default, /etc/shadow is only readable by the root user.
The Linux utility, unshadow, can be used to combine the two ﬁles in a format suited for password cracking utilities such as John the Ripper:
 # /usr/bin/unshadow /etc/passwd /etc/shadow > /tmp/crack.password.dbOther sub-techniques of OS Credential Dumping (8)
[1]
[2]
Version PermalinkID: T1003.008
Sub-technique of:  T1003

Tactic: Credential Access

Platforms: Linux

Permissions Required: root
Version: 1.0
Created: 11 February 2020
Last Modiﬁed: 20 March 2020
[3]3/22/24, 3:47 PM OS Credential Dumping: /etc/passwd and /etc/shadow, Sub-technique T1003.008 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1003/008/ 4/4References
1. The Linux Documentation Project. (n.d.). Linux Password and
Shadow File Formats. Retrieved February 19, 2020.
2. Vivek Gite. (2014, September 17). Linux Password Cracking:
Explain unshadow and john Commands (John the Ripper
Tool). Retrieved February 19, 2020.3. Zanni, A. (n.d.). The LaZagne Project !!!. Retrieved December
14, 2018.