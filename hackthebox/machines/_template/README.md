# [Nome da Máquina]

**OS:** Linux/Windows | **Dificuldade:** Very Easy/Easy/Medium/Hard | **Data:** DD/MM/AAAA | **IP:** `10.10.10.X`

## Resumo

> Uma linha descrevendo o vetor principal de ataque.

---

## Reconhecimento

```bash
nmap -sV -sC -p- --min-rate 5000 -oN scans/nmap_full.txt <IP>
```

![Nmap scan](screenshots/nmap.png)

**Serviços encontrados:**

| Porta | Protocolo | Serviço | Versão |
|-------|-----------|---------|--------|
|       |           |         |        |

---

## Enumeração

### [Serviço principal, ex: HTTP / FTP / SMB]

```bash
# comandos de enumeração
```

![Enumeração](screenshots/enum.png)

**Observações:**

---

## Exploração

```bash
# comandos de exploração
```

![Exploração](screenshots/exploit.png)

**Output relevante:**

```
[colar output aqui]
```

---

## Escalação de Privilégios

```bash
# sudo -l
# find / -perm -4000 2>/dev/null
# cat /etc/crontab
```

**Vetor encontrado:**

```bash
# comandos de privesc
```

---

## Flags

![Flag](screenshots/flag.png)

- User: `HTB{...}`
- Root: `HTB{...}`

---

## Lições Aprendidas

- **Vulnerabilidade:** o que estava errado na configuração/serviço
- **Mundo real:** onde essa falha aparece em ambientes corporativos
- **Defesa:** como mitigar esse vetor
