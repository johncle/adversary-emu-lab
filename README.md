# adversary-emu-lab

Educational lab for emulating how adversaries go through the [cyber kill chain](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html). We create a testing environment by running multiple VMs together

# TODO:

Create VMs for:

| Role                    | OS/Software                   | Purpose                                                  |
| ----------------------- | ----------------------------- | -------------------------------------------------------- |
| Attacker Machine        | Kali Linux                    | Conduct attacks (Metasploit, Cobalt Strike, BloodHound). |
| Victim Workstation      | Windows 10                    | Target machine for phishing, malware testing.            |
| Domain Controller (DC)  | Windows Server 2019           | Simulates Active Directory for enterprise attacks.       |
| Linux Server            | Ubuntu                        | Target for Linux-based attacks.                          |
| Log & Monitoring System | Security Onion / ELK / Splunk | SIEM for log analysis and detection.                     |

Implement each step of cyber kill chain plan:

-   [] Reconnaissance
-   [] Weaponization
-   [] Delivery
-   [] Exploitation
-   [] Installation
-   [] Command & Control (C2)
-   [] Actions on Objectives
    -   [] Privilege Escalation
    -   [] Lateral Movement
    -   [] Persistence & Evasion
    -   [] Exfiltration & Impact

# Cyber kill chain

## Reconnaissance

Harvesting email addresses, conference information, etc.

-   Tools: [nmap](https://nmap.org/), [theHarvester](https://github.com/laramies/theHarvester)

## Weaponization

Coupling exploit with backdoor into deliverable payload

-   Tools: [Metasploit](https://www.metasploit.com/)

## Delivery

Delivering weaponized bundle to the victim via email, web, USB, etc.

-   Tools: [SET (Social-Engineer Toolkit)](https://github.com/trustedsec/social-engineer-toolkit) for sending phishing emails with payloads

## Exploitation

Exploiting a vulnerability to execute code on victim's system

-   Tools: [Metasploit](https://www.metasploit.com/)

## Installation

Installing malware on the asset

-   Tools: [Metasploit](https://www.metasploit.com/)

## Command & Control (C2)

Command channel for remote manipulation of victim

-   Tools: [Metasploit](https://www.metasploit.com/)

## Actions on Objectives

With 'Hands on Keyboard' access, intruders accomplish their original goals

### Privilege Escalation

-   Windows: [Mimikatz](https://github.com/ParrotSec/mimikatz)/[WinPEAS](https://github.com/peass-ng/PEASS-ng) escalate privileges
-   Linux: [LinPEAS](https://github.com/peass-ng/PEASS-ng) to exploit misconfigurations

### Lateral Movement

-   Pass-the-Hash (PtH): [Mimikatz](https://github.com/ParrotSec/mimikatz) to steal and reuse credentials
-   Kerberoasting: [Rubeus](https://github.com/GhostPack/Rubeus) to extract and crack service account passwords

### Persistence & Evasion

-   Backdoors & Scheduled Tasks: [Metasploit](https://www.metasploit.com/) to maintain access
-   Payload Obfuscation: Use techniques from [Bypass-AV](https://github.com/matro7sh/BypassAV) to bypass antivirus

### Exfiltration & Impact

-   Data Exfiltration: Simulate stealing sensitive data via DNS tunneling, PowerShell, or C2 frameworks
-   Ransomware Simulation: Encrypt files in a sandbox to understand attack behaviors
