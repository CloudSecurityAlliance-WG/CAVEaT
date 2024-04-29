3/22/24, 3:33 PM Gather Victim Network Information: Network Trust Dependencies, Sub-technique T1590.003 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1590/003/ 1/1Thank you to Tidal Cyber and SOC Prime for becoming ATT&CK's ﬁrst Benefactors. To join the cohort, or learn more about this program visit our
Benefactors page.
Home>Techniques>Enterprise>Gather Victim Network Information>Network Trust Dependencies
Gather Victim Network Information: Network Trust
Dependencies
Mitigations
ID Mitigation Description
M1056 Pre-
compromiseThis technique cannot be easily mitigated with preventive controls since it is based on behaviors performed
outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount
and sensitivity of data available to external parties.
Detection
Much of this activity may have a very high occurrence and associated false positive rate, as well as potentially taking place outside the
visibility of the target organization, making detection diﬃcult for defenders.
Detection efforts may be focused on related stages of the adversary lifecycle, such as during Initial Access.
ReferencesAdversaries may gather information about the victim's network trust dependencies that can be used during targeting. Information about
network trusts may include a variety of details, including second or third-party organizations/domains (ex: managed service providers,
contractors, etc.) that have connected (and potentially elevated) network access.
Adversaries may gather this information in various ways, such as direct elicitation via Phishing for Information. Information about network
trusts may also be exposed to adversaries via online or other accessible data sets (ex: Search Open Technical Databases). Gathering this
information may reveal opportunities for other forms of reconnaissance (ex: Active Scanning or Search Open Websites/Domains),
establishing operational resources (ex: Acquire Infrastructure or Compromise Infrastructure), and/or initial access (ex: Trusted Relationship).Other sub-techniques of Gather Victim Network Information (6)
[1]
Version PermalinkID: T1590.003
Sub-technique of:  T1590

Tactic: Reconnaissance

Platforms: PRE
Version: 1.0
Created: 02 October 2020
Last Modiﬁed: 15 April 2021
1. García, C. (2019, April 3). Pentesting Active Directory Forests.
Retrieved October 20, 2020.