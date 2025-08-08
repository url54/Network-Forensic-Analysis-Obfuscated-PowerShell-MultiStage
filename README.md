# Download of Suspicious File

## Objective
Conducted a network forensic analysis of a multi-stage intrusion that leveraged obfuscated PowerShell to compromise a corporate endpoint. The objective was to dissect the attack by deobfuscating the initial stager, reconstructing the command-and-control (C2) signaling channel, and identifying the final payload. The investigation successfully traced the attacker's use of a legitimate remote access tool, TeamViewer, as a "Living Off the Land" technique to gain interactive control of the host and establish persistence.

## LAN Segment
- __LAN Segment Range__: 10.1.7.0/24 (10.1.17.0 through 10.1.17.255)
- __Domain__: bluemoontuesday.com
- __Active Directory (AD) Domain Controller__: 10.1.17.2 - WIN-GSH54QLW48D
- __AD Environment Name__: BLUEMOONTUESDAY
- __LAN Segment Gateway__: 10.1.17.1
- __LAN Segment Broadcast Address__: 10.1.17.255

## Key Highlights
- __Network Traffic Analysis__: Analyzed PCAP data to identify the full lifecycle of the attack, from initial payload delivery to C2 communication and final payload execution.
- __PowerShell Deobfuscation__: Manually deobfuscated malicious PowerShell scripts to uncover their true intent, including C2 server IP addresses and downloader functionality.
- __C2 Channel Analysis__: Identified and documented the attacker's covert C2 heartbeat mechanism, which used HTTP status codes (404/200) as a signaling channel to deliver commands.
- __"Living Off the Land" (LOLBin) Technique Identification__: Recognized the attacker's use of a legitimate, signed application (TeamViewer) to bypass security controls and establish remote access.
- __Persistence Mechanism Identification__: Uncovered evidence of persistence through the creation of a startup shortcut, as confirmed by analyzing the C2 traffic.
- __Indicator of Compromise (IOC) Extraction__: Identified and documented actionable IOCs, including the C2 server IP, malicious URIs, and the specific User-Agent string used by the stager.
- __MITRE ATT&CK Framework Mapping__: Mapped observed attacker behaviors to specific tactics and techniques in the MITRE ATT&CK framework, such as Bidirectional Communication (T1102.002) and Boot or Logon Autostart Execution (T1547.001).

## Final Report
[The final report](./Documents/PowerShellObfuscatedFinalReport.pdf)