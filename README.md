# 🔓 CTF Write-ups & Security Research

**Rafael Costa** — Engenheiro da Computação | AI Red Teamer | Brasília-DF

Write-ups detalhados de máquinas HackTheBox, CTFs e pesquisa em segurança ofensiva.
Cada write-up documenta o raciocínio completo: reconhecimento → exploração → escalação → lições aprendidas.

> Não documento apenas o que fiz. Documento **por que** funcionou e **onde** isso aparece no mundo real.

---

## 📊 Status

| Plataforma | Resolvidas | Dificuldade | Ranking |
|-----------|-----------|-------------|---------|
| HackTheBox Machines | X | Very Easy → Easy | Top Y% |
| HackTheBox Academy | AI Red Teamer Path | Em andamento | — |
| Bug Bounty | X reports | — | — |

## 📝 Write-ups Recentes

| # | Máquina | OS | Dificuldade | Vetor Principal | Data |
|---|---------|-----|------------|----------------|------|
| 001 | [Meow](./hackthebox/machines/meow/) | Linux | Very Easy | Telnet sem autenticação | 03/04/2026 |
| 002 | [Fawn](./hackthebox/machines/fawn/) | Linux | Very Easy | FTP anônimo | — |
| 003 | [Dancing](./hackthebox/machines/dancing/) | Windows | Very Easy | SMB share aberto | — |

## 🧠 Minha Metodologia

Documentei meu processo de ataque completo em [methodology/my-methodology.md](./methodology/my-methodology.md).

Resumo:

```
1. RECONHECIMENTO
   nmap -sV -sC -p- <target>
   Identificar OS, serviços, versões

2. ENUMERAÇÃO
   Por serviço: HTTP → gobuster/nikto | SMB → smbclient/enum4linux | FTP → login anônimo
   Buscar: credenciais default, arquivos expostos, versões vulneráveis

3. EXPLORAÇÃO
   Testar credenciais default/vazias primeiro
   Buscar exploit: searchsploit, Google "serviço versão exploit"
   Exploração manual antes de Metasploit

4. PÓS-EXPLORAÇÃO
   Pegar flag de user
   Enumerar: sudo -l, SUID (find / -perm -4000), cron, capabilities
   GTFOBins para binários com SUID/sudo

5. ESCALAÇÃO DE PRIVILÉGIOS
   Executar vetor identificado
   Pegar flag de root

6. DOCUMENTAÇÃO
   Write-up completo com comandos, output, screenshots
   Seção "Lições Aprendidas" obrigatória
```

## 📂 Estrutura do Repositório

```
.
├── README.md
├── methodology/
│   └── my-methodology.md
├── hackthebox/
│   ├── machines/
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
│   └── [evento]/[challenge]/
├── bug-bounty/
│   └── disclosed/
├── tools/
│   └── scripts customizados
└── cheatsheets/
    ├── nmap.md
    ├── linux-privesc.md
    ├── windows-privesc.md
    └── web-attacks.md
```

## 🛠 Template de Write-up

Cada write-up segue esta estrutura:

```markdown
# [Nome da Máquina]

**OS:** Linux/Windows | **Dificuldade:** Easy | **Data:** DD/MM/AAAA

## Resumo
Uma linha descrevendo o vetor principal de ataque.

## Reconhecimento
Nmap scan + análise de serviços.

## Enumeração
Investigação profunda do serviço vulnerável.

## Exploração
Passo a passo da exploração com comandos e output.

## Escalação de Privilégios
Como saí de user para root/admin.

## Flags
- User: `[hash]`
- Root: `[hash]`

## Lições Aprendidas
- O que esse ataque ensina sobre segurança no mundo real
- Onde essa vulnerabilidade aparece em ambientes corporativos
- Como defender contra esse vetor
```

## 🎯 Certificações em Andamento

- [ ] CompTIA Security+ (previsão: jun/2026)
- [ ] HTB Certified Defensive AI Expert (CDAE)
- [ ] HTB Certified Penetration Testing Specialist (CPTS)

## 📬 Contato

**Rafael Costa** — [LinkedIn](https://www.linkedin.com/in/rafael-costa-b1569b235/) | [Email](mailto:alves.rafasc@gmail.com) | [HackTheBox](https://app.hackthebox.com/users/3298107)

---

*Atualizado semanalmente. Cada máquina resolvida é documentada em até 24h.*