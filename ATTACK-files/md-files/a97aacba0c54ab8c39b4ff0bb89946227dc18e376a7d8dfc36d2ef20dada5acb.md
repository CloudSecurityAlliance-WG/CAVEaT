3/22/24, 3:45 PM Trusted Developer Utilities Proxy Execution: MSBuild, Sub-technique T1127.001 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1127/001/ 1/4Thank you to Tidal Cyber and SOC Prime for becoming ATT&CK's ﬁrst Benefactors. To join the cohort, or learn more about this program visit our
Benefactors page.3/22/24, 3:45 PM Trusted Developer Utilities Proxy Execution: MSBuild, Sub-technique T1127.001 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1127/001/ 2/4Home>Techniques>Enterprise>Trusted Developer Utilities Proxy Execution>MSBuild3/22/24, 3:45 PM Trusted Developer Utilities Proxy Execution: MSBuild, Sub-technique T1127.001 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1127/001/ 3/4Trusted Developer Utilities Proxy Execution: MSBuild
Procedure Examples
ID Name Description
S0363 Empire Empire can use built-in modules to abuse trusted utilities like MSBuild.exe.
C0001 Frankenstein During Frankenstein, the threat actors used MSbuild to execute an actor-created ﬁle.
S0013 PlugX A version of PlugX loads as shellcode within a .NET Framework project using msbuild.exe, presumably to
bypass application control techniques.
Mitigations
ID Mitigation Description
M1042 Disable or
Remove Feature
or ProgramMSBuild.exe may not be necessary within an environment and should be removed if not being used.
M1038 Execution
PreventionUse application control conﬁgured to block execution of msbuild.exe if it is not required for a given
system or network to prevent potential misuse by adversaries. For example, in Windows 10 and
Windows Server 2016 and above, Windows Defender Application Control (WDAC) policy rules may be
applied to block the msbuild.exe application and to prevent abuse.Adversaries may use MSBuild to proxy execution of code through a trusted Windows utility. MSBuild.exe (Microsoft Build Engine) is a
software build platform used by Visual Studio. It handles XML formatted project ﬁles that deﬁne requirements for loading and building
various platforms and conﬁgurations.
Adversaries can abuse MSBuild to proxy execution of malicious code. The inline task capability of MSBuild that was introduced in .NET
version 4 allows for C# or Visual Basic code to be inserted into an XML project ﬁle. MSBuild will compile and execute the inline task.
MSBuild.exe is a signed Microsoft binary, so when it is used this way it can execute arbitrary code and bypass application control defenses
that are conﬁgured to allow MSBuild.exe execution.[1]
[1][2]
[3]
Version PermalinkID: T1127.001
Sub-technique of:  T1127

Tactic: Defense Evasion

Platforms: Windows

System Requirements: .NET Framework version 4 or higher
Contributors: @ionstorm; Carrie Roberts, @OrOneEqualsOne
Version: 1.3
Created: 27 March 2020
Last Modiﬁed: 14 August 2023
[4]
[5]
[6]
[7]3/22/24, 3:45 PM Trusted Developer Utilities Proxy Execution: MSBuild, Sub-technique T1127.001 - Enterprise | MITRE ATT&CK®
https://attack.mitre.org/techniques/T1127/001/ 4/4Detection
ID Data SourceData Component Detects
DS0017 Command Command
ExecutionMonitor executed commands and arguments used before and after invocation of the utilities
may also be useful in determining the origin and purpose of the binary being executed.
DS0009 Process Process
CreationMonitor for newly executed processes of MSBuild.exe. Compare recent invocations of those
binaries with prior history of known good arguments and executed binaries to determine
anomalous and potentially adversarial activity.
Trusted developer utilities such as MSBuild may be leveraged to run malicious code with
elevated privileges. This analytic looks for any instances of msbuild.exe, which will execute
any C# code placed within a given XML document; and msxsl.exe, which processes xsl
transformation speciﬁcations for XML ﬁles and will execute a variaty of scripting languages
contained within the XSL ﬁle. Both of these executables are rarely used outside of Visual
Studio.
Analytic 1 - MSBuild and msxsl
target\_processes = filter processes where ( (exe="C:\Program Files
(x86)\Microsoft Visual Studio\*\bin\MSBuild.exe" OR
exe="C:\Windows\Microsoft.NET\Framework \msbuild.exe" OR
exe="C:\users\*\appdata\roaming\microsoft\msxsl.exe") AND
image\_path!=" Microsoft Visual Studio\*")
References
1. Microsoft. (n.d.). MSBuild1. Retrieved November 30, 2016.
2. Microsoft. (2017, September 21). MSBuild inline tasks.
Retrieved March 5, 2021.
3. LOLBAS. (n.d.). Msbuild.exe. Retrieved July 31, 2019.
4. Schroeder, W., Warner, J., Nelson, M. (n.d.). Github
PowerShellEmpire. Retrieved April 28, 2016.5. Adamitis, D. et al. (2019, June 4). It's alive: Threat actors
cobble together open-source pieces into monstrous
Frankenstein campaign. Retrieved May 11, 2020.
. Lancaster, T. and Idrizovic, E.. (2017, June 27). Paranoid
PlugX. Retrieved July 13, 2017.
7. Coulter, D. et al.. (2019, April 9). Microsoft recommended block
rules. Retrieved August 12, 2021.