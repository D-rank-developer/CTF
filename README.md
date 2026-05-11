# CTF Labs — Walkthroughs & Notes

A personal logbook of every Capture The Flag (CTF) lab I work through on my path into cybersecurity. Each lab gets its own write-up: what I tried, what failed, what worked, and what I learned. The point isn't to collect flags — it's to build the muscle memory of an offensive security mindset and have a public record of progress I can point to.

---

## 👋 About Me

I'm **Chamberlain**, an MSc Cyber Security student at the **University of Roehampton** based in London. I'm transitioning into cybersecurity from an IT support background, with a three-year plan that moves through cloud engineering into a security specialism (Red Team / SOC / AppSec — still narrowing it down).

My coursework so far has covered digital forensics, penetration testing, identity & Zero Trust, and ML for security — but coursework alone doesn't build the reflexes that hiring managers want to see. This repo is the practical side of the journey.

---

## 🎯 Why this repo exists

1. **Reinforce learning** — writing a lab up forces me to actually understand it, not just copy commands.
2. **Build a portfolio** — a public, dated, searchable record of skills for recruiters and hiring managers.
3. **Help others** — if someone gets stuck where I got stuck, my notes might unblock them.
4. **Track progress** — looking back at early write-ups vs recent ones is the clearest evidence of growth.

---

## 🧪 Platforms Covered

Labs in this repo come from (and will be tagged by) the following platforms:

- **TryHackMe** — guided learning paths, beginner-friendly rooms
- **Hack The Box** — machines, Starting Point, Academy modules
- **PortSwigger Web Security Academy** — web app vulnerabilities
- **VulnHub** — boot-to-root VMs
- **PicoCTF** — beginner-friendly Jeopardy-style challenges
- **OverTheWire** — wargames (Bandit, Natas, Leviathan, etc.)
- **Root Me** — short, focused challenges
- **CTFtime events** — live competitions when I can join

---

## 📂 Repo Structure

```
ctf-labs/
├── README.md                          ← you are here
├── tryhackme/
│   ├── <room-name>/
│   │   ├── README.md                  ← the write-up
│   │   ├── screenshots/
│   │   └── artifacts/                 ← payloads, scripts, exfiltrated files
│   └── ...
├── hackthebox/
│   ├── <machine-name>/
│   │   └── ...
├── portswigger/
│   └── <vulnerability-class>/
│       └── <lab-name>/
├── vulnhub/
├── picoctf/
├── overthewire/
├── ctf-events/
│   └── <event-name>-<year>/
└── tools-and-cheatsheets/
    ├── recon.md
    ├── web.md
    ├── privesc-linux.md
    ├── privesc-windows.md
    └── ...
```

Each lab folder is self-contained — you can land on it from a search engine and get the full picture without bouncing around.

---

## 🗂️ Categories Tracked

Every write-up is tagged with one or more of these so the repo stays searchable:

| Category | Examples |
|---|---|
| 🌐 Web Exploitation | SQLi, XSS, SSRF, IDOR, auth bypass, deserialization |
| 🐧 Linux Privilege Escalation | SUID, sudo abuse, cron, capabilities, kernel exploits |
| 🪟 Windows Privilege Escalation | Token impersonation, service misconfig, AD abuse |
| 🔍 Reconnaissance | nmap, gobuster, ffuf, subdomain enum, OSINT |
| 🔐 Cryptography | Classical ciphers, RSA attacks, hash cracking |
| 🧪 Reverse Engineering | Static/dynamic analysis, Ghidra, radare2, gdb |
| 💥 Binary Exploitation | Buffer overflows, ROP, format strings |
| 🕵️ Digital Forensics | Memory analysis (Volatility), disk imaging, registry, network captures |
| 📡 Network | Packet capture analysis, protocol abuse, pivoting |
| ☁️ Cloud Security | AWS/Azure misconfigs, IAM abuse, container escapes |
| 🏛️ Active Directory | Kerberoasting, AS-REP, BloodHound paths, DCSync |
| 🤖 OSINT | Geolocation, social media, metadata, public records |

---

## 📝 Write-Up Format

Every lab follows the same template so they're easy to compare and skim:

```markdown
# <Lab Name> — <Platform>

**Difficulty:** Easy / Medium / Hard
**Date completed:** YYYY-MM-DD
**Tags:** #web #sqli #linux-privesc
**Skills practised:** ...

## TL;DR
One-paragraph summary of the attack path.

## Reconnaissance
Commands run, what they returned, what stood out.

## Enumeration
Deeper digging — directory busting, service versions, hidden endpoints.

## Exploitation
The actual attack, step by step, with payloads and screenshots.

## Privilege Escalation
How I went from foothold to root/admin/SYSTEM.

## Flags
- User flag: ✅
- Root flag: ✅

## What I Learned
The bit I want to remember six months from now.

## Mistakes & Dead Ends
Honest notes on what I tried that didn't work — useful for future me.

## Defender's View
How this would have been prevented or detected. Ties exploitation back to blue-team thinking.
```

The **Defender's View** section is non-negotiable — understanding how to break things only matters if it informs how to defend them.

---

## 🛠️ My Working Toolkit

Tools I lean on most often (a non-exhaustive list, updated as I go):

**Recon & Enumeration** — `nmap`, `rustscan`, `gobuster`, `ffuf`, `feroxbuster`, `nikto`, `whatweb`, `wpscan`

**Web** — Burp Suite Community, `sqlmap`, browser DevTools, `curl`, custom Python with `requests`

**Exploitation** — `metasploit`, `msfvenom`, `searchsploit`, manual exploit dev

**Post-Exploitation / PrivEsc** — `linpeas`, `winpeas`, `pspy`, `BloodHound`, `mimikatz`, `chisel`

**Forensics & RE** — Autopsy, FTK Imager, Volatility 3, Ghidra, `strings`, `binwalk`

**Cracking** — `hashcat`, `john`, `hydra`

**Environment** — Kali Linux VM, occasional ParrotOS, custom tmux + zsh config


## 🎓 How This Connects to My Career Path

This repo is one pillar of a wider three-year transition plan:

- **Year 1 — Foundations:** IT support fundamentals, CompTIA A+/Network+, regular CTF practice (this repo).
- **Year 2 — Cloud:** AWS SAA or AZ-104, Security+, cloud-focused CTFs and labs (CloudGoat, flaws.cloud).
- **Year 3 — Security Specialisation:** OSCP / CySA+ / AWS Security Specialty, harder boxes, original research and reports.

The labs in this repo evolve with that arc — expect more cloud and AD-heavy content over time.

---

