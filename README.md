# TryHackMe Writeups

Penetration testing reports and room writeups from my TryHackMe journey. Each report documents the full attack chain — reconnaissance, exploitation, privilege escalation, and lessons learned — written the way a real engagement report would be.

---

## Rooms Completed

| Room | Difficulty | OS | Key Techniques | Report |
|------|-----------|-----|----------------|--------|
| **Nmap** | Easy | Linux | Port scanning, scan types, service fingerprinting, flag usage | [View PDF](./Nmap_Recap.pdf) |
| **Blue** | Easy | Windows | EternalBlue (MS17-010), Metasploit, hashdump, NTLM hash cracking with John the Ripper | [View PDF](./blue_room_recap.pdf) |
| **Ice** | Easy | Windows | Icecast buffer overflow, process migration, UAC bypass (bypassuac_eventvwr), getsystem, Mimikatz / Kiwi credential dumping | [View PDF](./Ice_Recap.pdf) |
| **Blaster** | Easy | Windows | Web enumeration (gobuster), IIS directory fuzzing, RDP via xfreerdp, CVE-2019-1388 UAC bypass, Meterpreter web_delivery, registry persistence | [View PDF](./Blaster_Room_Recap.pdf) |
| **Anthem** | Easy | Windows | Web enumeration, robots.txt, HTML source analysis, OSINT, RDP access, Windows DACL ownership abuse for privilege escalation | [View PDF](./Anthem_Room_Recap.pdf) |
| **Relevant** | Medium | Windows | Full port scanning, anonymous SMB enumeration, Base64 credential decoding, ASPX webshell via writable SMB share, SeImpersonatePrivilege, PrintSpoofer | [View PDF](./Relevant_Room_Recap.pdf) |

---

## Skills Covered

**Reconnaissance**
- Nmap full and targeted scans, service version detection, NSE scripts
- SMB enumeration with smbclient
- Web directory brute-forcing with gobuster
- OSINT and HTML source analysis

**Exploitation**
- Metasploit framework — search, use, set, run
- Public CVE exploitation (MS17-010 EternalBlue, Icecast, CVE-2019-1388)
- Manual ASPX webshell generation with msfvenom
- RDP access via xfreerdp
- Reverse shell setup and listener management with netcat

**Post-Exploitation**
- Process migration and session management in Meterpreter
- Credential dumping with Mimikatz / Kiwi
- NTLM hash cracking with John the Ripper
- Windows file permission and DACL abuse
- Registry-based persistence

**Privilege Escalation**
- UAC bypass techniques (bypassuac_eventvwr, CVE-2019-1388)
- getsystem in Metasploit
- SeImpersonatePrivilege exploitation with PrintSpoofer
- Token impersonation on Windows Server 2016

**Tools Used**
`nmap` `metasploit` `msfvenom` `smbclient` `gobuster` `xfreerdp` `netcat` `john` `mimikatz` `printspoofer` `certutil` `base64` `python3`

---

## Report Format

Every report follows a consistent structure:

1. Introduction and target summary
2. Phase-by-phase attack walkthrough with all commands used
3. Problems encountered and how they were resolved
4. Tools and technologies table
5. Key learnings
6. Engagement summary

Reports are written to be readable by both technical and non-technical audiences.

---

## About

Level 4 Computer Science student at the University of Hertfordshire, working through TryHackMe rooms to build hands-on penetration testing skills alongside my degree. Background in embedded systems (ESP32, MicroPython), networking (Cisco Packet Tracer, VLANs), and software engineering (Java, Agile).

**Made by Salah Mohamed**
