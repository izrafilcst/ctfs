# [Machine Name]

**OS:** Linux/Windows | **Difficulty:** Very Easy/Easy/Medium/Hard | **Date:** DD/MM/YYYY | **IP:** `10.10.10.X`

## Summary

> One line describing the main attack vector.

---

## Reconnaissance

```bash
nmap -sV -sC -p- --min-rate 5000 -oN scans/nmap_full.txt <IP>
```

![Nmap scan](screenshots/nmap.png)

**Services found:**

| Port | Protocol | Service | Version |
|------|----------|---------|---------|
|      |          |         |         |

---

## Enumeration

### [Main service, e.g.: HTTP / FTP / SMB]

```bash
# enumeration commands
```

![Enumeration](screenshots/enum.png)

**Observations:**

---

## Exploitation

```bash
# exploitation commands
```

![Exploitation](screenshots/exploit.png)

**Relevant output:**

```
[paste output here]
```

---

## Privilege Escalation

```bash
# sudo -l
# find / -perm -4000 2>/dev/null
# cat /etc/crontab
```

**Vector found:**

```bash
# privesc commands
```

---

## Flags

![Flag](screenshots/flag.png)

- User: `HTB{...}`
- Root: `HTB{...}`

---

## Lessons Learned

- **Vulnerability:** what was misconfigured/broken in the service
- **Real world:** where this flaw appears in corporate environments
- **Defense:** how to mitigate this vector
