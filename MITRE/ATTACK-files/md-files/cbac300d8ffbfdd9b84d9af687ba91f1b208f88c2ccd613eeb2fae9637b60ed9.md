3/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 1/6Thank you to Tidal Cyber and SOC Prime for becoming ATT&CK's ﬁrst Benefactors. To join the cohort, or learn more about this program visit our
Benefactors page.3/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 2/6Home>Techniques>Enterprise>Clipboard Data3/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 3/6Clipboard Data
Adversaries may collect data stored in the clipboard from users copying information within or between applications.
For example, on Windows adversaries can access clipboard data by using clip.exe or Get-Clipboard . Additionally, adversaries may
monitor then replace users’ clipboard with their data (e.g., Transmitted Data Manipulation).
macOS and Linux also have commands, such as pbpaste , to grab clipboard contents.[1][2][3]
[4]
[5]
Version PermalinkID: T1115
Sub-techniques:  No sub-techniques

Tactic: Collection

Platforms: Linux, Windows, macOS
Version: 1.2
Created: 31 May 2017
Last Modiﬁed: 14 April 20233/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 4/6Procedure Examples
ID Name Description
S0331 Agent Tesla Agent Tesla can steal data from the victim’s clipboard.
G0082 APT38 APT38 used a Trojan called KEYLIME to collect data from the clipboard.
G0087 APT39 APT39 has used tools capable of stealing contents of the clipboard.
S0373 Astaroth Astaroth collects information from the clipboard by using the OpenClipboard() and GetClipboardData()
libraries. 
S0438 Attor Attor has a plugin that collects data stored in the Windows clipboard by using the OpenClipboard and
GetClipboardData APIs.
S0454 Cadelspy Cadelspy has the ability to steal data from the clipboard.
S0261 Catchamas Catchamas steals data stored in the clipboard.
S0660 Clambling Clambling has the ability to capture and store clipboard data.
S0050 CosmicDuke CosmicDuke copies and exﬁltrates the clipboard contents every 30 seconds.
S0334 DarkComet DarkComet can steal data from the clipboard.
S1066 DarkTortilla DarkTortilla can download a clipboard information stealer module.
S0363 Empire Empire can harvest clipboard data on both Windows and macOS systems.
S0569 Explosive Explosive has a function to use the OpenClipboard wrapper.
S0381 FlawedAmmyy FlawedAmmyy can collect clipboard data.
S0531 Grandoreiro Grandoreiro can capture clipboard data from a compromised host.
S0170 Helminth The executable version of Helminth has a module to log clipboard contents.
S0044 JHUHUGIT A JHUHUGIT variant accesses a screenshot saved in the clipboard and converts it to a JPG image.
S0283 jRAT jRAT can capture clipboard data.
S0250 Koadic Koadic can retrieve the current content of the user clipboard.
S0356 KONNI KONNI had a feature to steal data from the clipboard.
S0409 Machete Machete hijacks the clipboard data by creating an overlapped window that listens to keyboard events.
S0282 MacSpy MacSpy can steal clipboard contents.
S0652 MarkiRAT MarkiRAT can capture clipboard content.
S0530 Melcoz Melcoz can monitor content saved to the clipboard.
S0455 Metamorfo Metamorfo has a function to hijack data from the clipboard by monitoring the contents of the clipboard
and replacing the cryptocurrency wallet with the attacker's.
C0014 Operation
WocaoDuring Operation Wocao, threat actors collected clipboard data in plaintext.[6][7][8][9]
[10]
[11]
[12]
[13]
[14]
[15]
[16][17]
[18]
[19]
[20]
[21]
[22]
[23]
[24]
[25]
[26]
[27]
[28]
[29]
[30]
[31]
[32]
[33]
[34]
[35][36]
[37]3/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 5/6ID Name Description
S0332 Remcos Remcos steals and modiﬁes data from the clipboard.
S0375 Remexi Remexi collects text from the clipboard.
S0240 ROKRAT ROKRAT can extract clipboard data from a compromised host.
S0148 RTM RTM collects data from the clipboard.
S0253 RunningRAT RunningRAT contains code to open and copy data from the clipboard.
S0467 TajMahal TajMahal has the ability to steal data from the clipboard of an infected host.
S0004 TinyZBot TinyZBot contains functionality to collect information from the clipboard.
S0257 VERMIN VERMIN collects data stored in the clipboard.
S0330 Zeus Panda Zeus Panda can hook GetClipboardData function to watch for clipboard pastes to collect.
Mitigations
This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of system features.
Detection
ID Data SourceData Component Detects
DS0017 Command Command
ExecutionMonitor executed commands and arguments to collect data stored in the clipboard from
users copying information within or between applications.
DS0009 Process OS API Execution Monitor API calls that could collect data stored in the clipboard from users copying
information within or between applications.[38]
[39]
[40]
[41][42]
[43]
[44]
[45]
[46]
[47]3/22/24, 3:50 PM Clipboard Data, Technique T1115 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1115/ 6/6References
1. Microsoft. (n.d.). About the Clipboard. Retrieved March 29,
2016.
2. Microsoft, JasonGerend, et al. (2023, February 3). clip.
Retrieved June 21, 2022.
3. CISA. (2021, August 20). Alert (AA21-200B) Chinese State-
Sponsored Cyber Operations: Observed TTPs. Retrieved June
21, 2022.
4. Maljic, T. (2020, April 16). Mining for malicious Ruby gems.
Retrieved October 15, 2022.
5. rvrsh3ll. (2016, May 18). Operating with EmPyre. Retrieved
July 12, 2017.
. Brumaghin, E., et al. (2018, October 15). Old dog, new tricks -
Analysing new RTF-based campaign distributing Agent Tesla,
Loki with PyREbox. Retrieved November 5, 2018.
7. Zhang, X. (2018, April 05). Analysis of New Agent Tesla
Spyware Variant. Retrieved November 5, 2018.
. Zhang, X. (2017, June 28). In-Depth Analysis of A New Variant
of .NET Malware AgentTesla. Retrieved November 5, 2018.
9. Arsene, L. (2020, April 21). Oil & Gas Spearphishing
Campaigns Drop Agent Tesla Spyware in Advance of Historic
OPEC+ Deal. Retrieved May 19, 2020.
10. FireEye. (2018, October 03). APT38: Un-usual Suspects.
Retrieved November 6, 2018.
11. Symantec. (2018, February 28). Chafer: Latest Attacks Reveal
Heightened Ambitions. Retrieved May 22, 2020.
12. Salem, E. (2019, February 13). ASTAROTH MALWARE USES
LEGITIMATE OS AND ANTIVIRUS PROCESSES TO STEAL
PASSWORDS AND PERSONAL DATA. Retrieved April 17, 2019.
13. Hromcova, Z. (2019, October). AT COMMANDS, TOR-BASED
COMMUNICATIONS: MEET ATTOR, A FANTASY CREATURE
AND ALSO A SPY PLATFORM. Retrieved May 6, 2020.
14. Symantec Security Response. (2015, December 7). Iran-based
attackers use back door threats to spy on Middle Eastern
targets. Retrieved April 17, 2019.
15. Balanza, M. (2018, April 02). Infostealer.Catchamas. Retrieved
July 10, 2018.
1. Lunghi, D. et al. (2020, February). Uncovering DRBControl.
Retrieved November 12, 2021.
17. Chen, T. and Chen, Z. (2020, February 17). CLAMBLING - A
New Backdoor Base On Dropbox. Retrieved November 12,
2021.
1. F-Secure Labs. (2014, July). COSMICDUKE Cosmu with a twist
of MiniDuke. Retrieved July 3, 2014.
19. Kujawa, A. (2018, March 27). You dirty RAT! Part 1:
DarkComet. Retrieved November 6, 2018.
20. Secureworks Counter Threat Unit Research Team. (2022,
August 17). DarkTortilla Malware Analysis. Retrieved
November 3, 2022.
21. Schroeder, W., Warner, J., Nelson, M. (n.d.). Github
PowerShellEmpire. Retrieved April 28, 2016.
22. Threat Intelligence and Research. (2015, March 30). VOLATILE
CEDAR. Retrieved February 8, 2021.
23. Financial Security Institute. (2020, February 28). Proﬁling of
TA505 Threat Group That Continues to Attack the Financial
Sector. Retrieved July 14, 2022.
24. Abramov, D. (2020, April 13). Grandoreiro Malware Now
Targeting Banks in Spain. Retrieved November 12, 2020.25. Falcone, R. and Lee, B.. (2016, May 26). The OilRig Campaign:
Attacks on Saudi Arabian Organizations Deliver Helminth
Backdoor. Retrieved May 3, 2017.
2. Unit 42. (2017, December 15). Unit 42 Playbook Viewer.
Retrieved December 20, 2017.
27. Kamluk, V. & Gostev, A. (2016, February). Adwind - A Cross-
Platform RAT. Retrieved April 23, 2019.
2. Magius, J., et al. (2017, July 19). Koadic. Retrieved June 18,
2018.
29. Rascagneres, P. (2017, May 03). KONNI: A Malware Under The
Radar For Years. Retrieved November 5, 2018.
30. ESET. (2019, July). MACHETE JUST GOT SHARPER
Venezuelan government institutions under attack. Retrieved
September 13, 2019.
31. Kaspersky Global Research and Analysis Team. (2014, August
20). El Machete. Retrieved September 13, 2019.
32. Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved
September 21, 2018.
33. GReAT. (2021, June 16). Ferocious Kitten: 6 Years of Covert
Surveillance in Iran. Retrieved September 22, 2021.
34. GReAT. (2020, July 14). The Tetrade: Brazilian banking
malware goes global. Retrieved November 9, 2020.
35. Zhang, X. (2020, February 4). Another Metamorfo Variant
Targeting Customers of Financial Institutions in More
Countries. Retrieved July 30, 2020.
3. ESET Research. (2019, October 3). Casbaneiro: peculiarities of
this banking Trojan that affects Brazil and Mexico. Retrieved
September 23, 2021.
37. Dantzig, M. v., Schamper, E. (2019, December 19). Operation
Wocao: Shining a light on one of China’s hidden hacking
groups. Retrieved October 8, 2020.
3. Klijnsma, Y. (2018, January 23). Espionage Campaign
Leverages Spear Phishing, RATs Against Turkish Defense
Contractors. Retrieved November 6, 2018.
39. Legezo, D. (2019, January 30). Chafer used Remexi malware
to spy on Iran-based foreign diplomatic entities. Retrieved
April 17, 2019.
40. Cash, D., Grunzweig, J., Adair, S., Lancaster, T. (2021, August
25). North Korean BLUELIGHT Special: InkySquid Deploys
RokRAT. Retrieved October 1, 2021.
41. Faou, M. and Boutin, J. (2017, February). Read The Manual: A
Guide to the RTM Banking Trojan. Retrieved March 9, 2017.
42. Duncan, B., Harbison, M. (2019, January 23). Russian
Language Malspam Pushing Redaman Banking Malware.
Retrieved June 16, 2020.
43. Sherstobitoff, R., Saavedra-Morales, J. (2018, February 02).
Gold Dragon Widens Olympics Malware Attacks, Gains
Permanent Presence on Victims’ Systems. Retrieved June 6,
2018.
44. GReAT. (2019, April 10). Project TajMahal – a sophisticated
new APT framework. Retrieved October 14, 2019.
45. Cylance. (2014, December). Operation Cleaver. Retrieved
September 14, 2017.
4. Lancaster, T., Cortes, J. (2018, January 29). VERMIN: Quasar
RAT and Custom Malware Used In Ukraine. Retrieved July 5,
2018.
47. Ebach, L. (2017, June 22). Analysis Results of
Zeus.Variant.Panda. Retrieved November 5, 2018.