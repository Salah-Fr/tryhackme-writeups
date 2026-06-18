# TryHackMe Writeups

[![TryHackMe](https://img.shields.io/badge/TryHackMe-SalahFr-red?style=for-the-badge&logo=tryhackme&logoColor=white)](https://tryhackme.com/p/SalahFr)


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
| **Protocols and Servers (1 & 2)** | Easy | Linux | Manual protocol interaction via Telnet (HTTP, FTP, SMTP, POP3, IMAP), cleartext credential sniffing (tcpdump/Wireshark), MITM theory (ARP/DNS spoofing, SSL stripping), TLS/SSH mitigations, Hydra dictionary attack against IMAP | [View PDF](./Protocols_and_Servers_Report.pdf) |
| **Guided Pentest: Web** | Medium | Linux | HTTP header analysis, Gobuster directory enumeration, IDOR user enumeration, broken password reset (account takeover), file upload filter bypass (.phtml), PHP web shell, reverse shell, RCE as www-data | [View PDF](./Web_Pentest_Report_RecruitX.pdf) |
| **Guided Pentest: Infrastructure** | Medium | Linux | Nmap service fingerprinting, searchsploit CVE research, UnrealIRCd backdoor exploitation (CVE-2010-2075), reverse shell via Metasploit, plaintext credential discovery, SSH privilege escalation to root | [View PDF](./Guided_Pentest_Infrastructure_Report.pdf) |
| **Modern Web Stacks** | Easy | Linux | Passive stack fingerprinting (HTTP headers, cookies, page-source artifacts), prototype pollution to admin takeover (MERN/Express), Next.js middleware auth bypass (CVE-2025-29927), error-based SQL injection (CVE-2021-35042, Django), Apache path traversal to unauthenticated RCE (CVE-2021-41773) | [View PDF](./Modern_Web_Stacks_Report.pdf) |
| **Web Server Attacks II** | Medium | Windows | IIS 10.0 fingerprinting, HTTP banner grabbing, WebDAV detection, IIS tilde (8.3 short filename) enumeration, backup directory credential discovery, authenticated WebDAV ASPX shell upload (NTLM), post-exploitation identity and SeImpersonatePrivilege analysis, IIS misconfiguration review (directory listing, web.config exposure), Nmap NSE automation | [View PDF](./Web_Server_Attacks_II_Report.pdf) |

---

## Skills Covered

**Reconnaissance**
- Nmap full and targeted scans, service version detection, NSE scripts
- SMB enumeration with smbclient
- Web directory brute-forcing with gobuster
- HTTP header analysis and technology stack fingerprinting
- Passive web stack identification across MERN, Next.js, Django, and LAMP from headers, cookie names, and HTML source artifacts
- IDOR-based user enumeration via URL parameter manipulation
- API endpoint enumeration without authentication
- OSINT and HTML source analysis
- IRC service fingerprinting and version disclosure
- Manual protocol interaction with raw Telnet client (HTTP, FTP, SMTP, POP3, IMAP)
- Service banner grabbing and version disclosure analysis
- IIS tilde (8.3 short filename) enumeration for hidden directory discovery
- WebDAV detection via HTTP OPTIONS and DAV response headers

**Exploitation**
- Metasploit framework — search, use, set, run
- Public CVE exploitation (MS17-010 EternalBlue, Icecast, CVE-2019-1388, CVE-2010-2075)
- Modern web framework CVE exploitation (Next.js CVE-2025-29927, Django CVE-2021-35042, Apache CVE-2021-41773)
- Supply chain backdoor exploitation (UnrealIRCd 3.2.8.1)
- Prototype pollution via unfiltered recursive merge (Object.prototype injection)
- Next.js middleware authentication bypass via trusted internal header (x-middleware-subrequest)
- Error-based SQL injection using updatexml() XPath error extraction
- Apache path traversal via encoded-dot filter bypass chained with mod_cgi for RCE
- Reverse shell payload configuration and port selection (443 firewall evasion)
- Manual ASPX webshell generation with msfvenom
- Broken authentication abuse — password reset token interception
- File upload filter bypass using alternative PHP extensions (.phtml)
- PHP web shell deployment and command execution
- RDP access via xfreerdp
- Reverse shell setup and listener management with netcat
- Passive credential sniffing with tcpdump and Wireshark display filters
- SMTP email spoofing via unverified mail from: header
- Dictionary attack against IMAP authentication with THC Hydra + rockyou.txt
- Authenticated WebDAV ASPX shell upload via NTLM over HTTP

**Post-Exploitation**
- Process migration and session management in Meterpreter
- Credential dumping with Mimikatz / Kiwi
- NTLM hash cracking with John the Ripper
- Windows file permission and DACL abuse
- Registry-based persistence
- Server enumeration via web shell (whoami, hostname, /etc/passwd)
- Filesystem enumeration for sensitive files (find / -name password*)
- Plaintext credential extraction from world-readable files
- Raw shell stabilisation and binary-level password verification with xxd
- Unauthenticated command execution and file read via CGI (id, cat /etc/passwd, cat /flag.txt)
- IIS application pool identity enumeration and SeImpersonatePrivilege identification

**Privilege Escalation**
- UAC bypass techniques (bypassuac_eventvwr, CVE-2019-1388)
- getsystem in Metasploit
- SeImpersonatePrivilege exploitation with PrintSpoofer
- Token impersonation on Windows Server 2016
- Plaintext root credential abuse via SSH after low-privilege foothold
- Application-level privilege escalation via prototype pollution (isAdmin bypass)

**Web Application**
- OWASP-aligned manual testing methodology
- Modern web stack identification and version confirmation before exploitation
- Prototype pollution and JavaScript object inheritance abuse
- Trust boundary failure analysis (framework-internal headers, unsanitised JSON merges)
- SQL injection through raw query construction that bypasses the ORM
- IDOR (Insecure Direct Object Reference) identification and exploitation
- Broken password reset mechanism abuse
- Client-side vs server-side restriction bypass
- File upload allowlist vs blocklist security analysis
- Cookie security flag analysis (HttpOnly, Secure)
- Unauthenticated API endpoint disclosure
- IIS misconfiguration identification (directory listing, exposed web.config, verbose headers, TRACE method)

**Network Protocols & Cryptography**
- Cleartext protocol mechanics (Telnet, HTTP, FTP, SMTP, POP3, IMAP)
- Sniffing attacks and packet capture analysis (tcpdump, Wireshark)
- MITM attack techniques (ARP spoofing, DNS spoofing, rogue AP, SSL stripping)
- TLS/SSL handshake and certificate trust model
- Secure protocol upgrades (HTTPS, FTPS, SMTPS, POP3S, IMAPS, DoT)
- SSH key-based authentication and secure file transfer (SCP, SFTP)
- CIA triad and DAD attack mapping
- NTLM challenge-response authentication over HTTP

**Tools Used**

`nmap` `metasploit` `msfvenom` `smbclient` `gobuster` `xfreerdp` `netcat` `john` `mimikatz` `printspoofer` `certutil` `base64` `python3` `curl` `grep` `burpsuite` `searchsploit` `ssh` `xxd` `tcpdump` `wireshark` `hydra` `telnet` `ftp` `scp` `cadaver` `iis_shortname_scan.py`

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
