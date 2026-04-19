# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a personal CTF write-ups and security research documentation repository by Rafael Costa. It contains write-ups for HackTheBox machines, CTF competitions, and bug bounty disclosures — all in Markdown. There is no build system, test suite, or code to compile.

## Write-up Structure

Every machine write-up lives under `hackthebox/machines/<name>/` and must follow this template:

```markdown
# [Nome da Máquina]

**OS:** Linux/Windows | **Dificuldade:** Easy | **Data:** DD/MM/AAAA

## Resumo
## Reconhecimento
## Enumeração
## Exploração
## Escalação de Privilégios
## Flags
- User: `[hash]`
- Root: `[hash]`
## Lições Aprendidas
```

The "Lições Aprendidas" section is mandatory and must cover real-world implications and defenses.

## Attack Methodology

Document each phase in order: Reconhecimento → Enumeração → Exploração → Pós-Exploração → Escalação → Documentação. Always attempt manual exploitation before Metasploit. Include full command output, not just commands.

## Repository Layout

- `hackthebox/machines/<name>/` — one folder per machine with `README.md`, `scans/`, `screenshots/`
- `hackthebox/academy/` — academy path notes
- `ctf-competitions/<event>/<challenge>/` — competition write-ups
- `bug-bounty/disclosed/` — disclosed bug bounty reports
- `tools/` — custom scripts
- `cheatsheets/` — reference sheets (nmap, linux-privesc, windows-privesc, web-attacks)
- `methodology/my-methodology.md` — full attack methodology documentation

## README Index Maintenance

When adding a new machine, update the `## 📝 Write-ups Recentes` table in `README.md` with the sequential number, machine name (linked), OS, difficulty, main attack vector, and date.

## Commit Convention

Commit messages use only the machine name, lowercase. Examples:

```
meow
fawn
dancing
```
