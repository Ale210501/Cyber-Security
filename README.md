# Red Horse - Social Engineering Attack Simulation with Trojan Payload

## Overview

**Red Horse** is a university cybersecurity project designed to simulate a black-box penetration test using social engineering techniques. The scenario involves impersonating tipsters within a Telegram group to lure victims into downloading a malicious file hidden behind a sports betting suggestion. The objective is to raise awareness about malware distribution tactics and defensive countermeasures.

## Objectives

- Create and deliver a payload to a Windows victim via Telegram.
- Establish a reverse TCP connection using Metasploit.
- Demonstrate post-exploitation steps: file manipulation, screen sharing, and ransomware tactics.
- Implement blue team strategies to detect, prevent, and respond to such attacks.
- Develop an educational Serious Game: **Cyber Quiz**.

## Tools and Technologies

- **Kali Linux VM**:
  - `msfvenom` – for generating the payload.
  - `msfconsole` – for handling reverse shell sessions.
- **Windows 10 VMs**:
  - One as attacker (for packaging the trojan).
  - One as victim.
- **WinRAR** – to create self-extracting archives (SFX).
- **Telegram** – to simulate real-world social engineering via a fake betting group.
- **Convertio** – to convert images to `.ico` format for disguise.

## Kill Chain Phases

1. **Reconnaissance**  
   Targeted sports bettors through Telegram, leveraging trust in tipster groups.

2. **Weaponization**  
   Created a reverse TCP payload using `msfvenom`, encoded it using `shikata_ga_nai`, and packed it with an image in a `.zip` file disguised as a betting slip.

3. **Delivery**  
   Delivered the `.zip` archive through a Telegram channel (`RedHorse Bet`).

4. **Exploitation**  
   Victim executed the SFX archive, triggering the payload and opening a reverse shell to the attacker's Kali machine.

5. **Installation**  
   Established remote access using Meterpreter and enabled screen sharing.

6. **Command and Control (C2)**  
   Navigated the victim’s file system, exfiltrated data, and deployed a ransomware script to encrypt personal files.

7. **Actions on Objectives**  
   Demanded ransom via a text file and later provided a script to decrypt the data after "payment."

## Blue Team Defense Strategies

### Detection
- Antivirus scans (e.g., Windows Defender, Norton).
- Steganalysis tools to inspect hidden data in media.
- Digital forensics tools (e.g., Autopsy, FTK Imager).

### Prevention
- Web gateway filters for suspicious downloads.
- User training on phishing and malware awareness.

### Incident Response
- Immediate network isolation.
- Malware removal and system patching.
- Monitoring with SIEM and centralized logging tools.

## Ethical and Legal Considerations

This simulation was performed in a controlled lab environment with virtual machines and no real-world systems were harmed. Malware testing and penetration tests must **always** be conducted with explicit authorization to avoid legal consequences and ethical violations.

## Serious Game: Cyber Quiz

An interactive quiz game designed to educate users on:
- How to recognize and avoid trojans.
- Understanding malware behavior.
- Proper responses to security threats.

### Link to Game
Play here: [https://cyberquiz.my.canva.site/](https://cyberquiz.my.canva.site/)

### Preview Video
Watch: [https://bit.ly/VideoCyberQuiz](https://bit.ly/VideoCyberQuiz)

---

> This project is for educational purposes only and must not be replicated outside authorized environments.
