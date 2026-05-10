# 🔓 CTF Write-ups & Security Research

**Rafael Costa** — Computer Engineer | AI Red Teamer | Brasília-DF

Detailed write-ups for HackTheBox machines, CTFs, and offensive security research.
Each write-up documents the full reasoning: reconnaissance → exploitation → escalation → lessons learned.

> I don't just document what I did. I document **why** it worked and **where** it shows up in the real world.

---

## 📊 Status

| Platform | Solved | Difficulty | Ranking |
|----------|--------|------------|---------|
| HackTheBox Machines | X | Very Easy → Easy | Top Y% |
| HackTheBox Academy | AI Red Teamer Path | In progress | — |
| Bug Bounty | X reports | — | — |

## 📝 Recent Write-ups

| # | Machine | OS | Difficulty | Main Vector | Date |
|---|---------|-----|-----------|-------------|------|
| 001 | [Meow](./hackthebox/machines/meow/) | Linux | Very Easy | Telnet without authentication | 03/04/2026 |
| 002 | [Fawn](./hackthebox/machines/fawn/) | Linux | Very Easy | Anonymous FTP | 21/04/2026 |
| 003 | [Dancing](./hackthebox/machines/dancing/) | Windows | Very Easy | Open SMB share | — |

## 🧠 My Methodology

```
1. RECONNAISSANCE
   nmap -sV -sC -p- <target>
   Identify OS, services, versions

2. ENUMERATION
   Per service: HTTP → gobuster/nikto | SMB → smbclient/enum4linux | FTP → anonymous login
   Look for: default credentials, exposed files, vulnerable versions

3. EXPLOITATION
   Test default/empty credentials first
   Search for exploits: searchsploit, Google "service version exploit"
   Manual exploitation before Metasploit

4. POST-EXPLOITATION
   Grab user flag
   Enumerate: sudo -l, SUID (find / -perm -4000), cron, capabilities
   GTFOBins for binaries with SUID/sudo

5. PRIVILEGE ESCALATION
   Execute identified vector
   Grab root flag

6. DOCUMENTATION
   Full write-up with commands, output, screenshots
   Mandatory "Lessons Learned" section
```

## 📂 Repository Structure

```
.
├── README.md
├── hackthebox/
│   ├── machines/
│   │   ├── _template/
│   │   ├── meow/
│   │   │   ├── README.md
│   │   │   ├── scans/
│   │   │   └── screenshots/
│   │   ├── fawn/
│   │   └── dancing/
│   └── academy/
│       ├── ai-red-teamer/
│       └── penetration-tester/
├── ctf-competitions/
│   └── [event]/[challenge]/
├── bug-bounty/
│   └── disclosed/
├── tools/
└── cheatsheets/
    ├── nmap.md
    ├── linux-privesc.md
    ├── windows-privesc.md
    └── web-attacks.md
```

## 🛠 Write-up Template

Each write-up follows this structure:

```markdown
# [Machine Name]

**OS:** Linux/Windows | **Difficulty:** Easy | **Date:** DD/MM/YYYY

## Summary
One line describing the main attack vector.

## Reconnaissance
Nmap scan + service analysis.

## Enumeration
Deep investigation of the vulnerable service.

## Exploitation
Step-by-step exploitation with commands and output.

## Privilege Escalation
How I moved from user to root/admin.

## Flags
- User: `[hash]`
- Root: `[hash]`

## Lessons Learned
- What this attack teaches about real-world security
- Where this vulnerability appears in corporate environments
- How to defend against this vector
```

## 🎯 Certifications in Progress

- [ ] CompTIA Security+ (expected: Jun/2026)
- [ ] HTB Certified Defensive AI Expert (CDAE)
- [ ] HTB Certified Penetration Testing Specialist (CPTS)

## 📬 Contact

**Rafael Costa** — [LinkedIn](https://www.linkedin.com/in/rafael-costa-b1569b235/) | [Email](mailto:alves.rafasc@gmail.com) | [HackTheBox](https://app.hackthebox.com/users/3298107)

---

*Updated weekly. Each solved machine is documented within 24h.*
