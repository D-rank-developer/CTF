# West Tech: Contain the AI — Incident Response Writeup

> **Category:** Incident Response · Digital Forensics · AI-Assisted Investigation
> **Difficulty:** Medium
> 📄 **Full walkthrough with screenshots and commands:** [`West_Tech_Writeup.pdf`](./West_Tech_Writeup.pdf)

---

## Scenario

A senior researcher at West Tech (a classified defence contractor) had their workstation compromised. A ransom note on the desktop demanded **0.853 BTC** and taunted that the on-host AI assistant had been the leak source. The job: investigate the intrusion, recover the encrypted project files, and identify the flag — without trusting the AI blindly.

---

## Approach

1. **SSH'd in** to the compromised workstation as `o.deer`.
2. **Read the ransom note** (`pwned.txt`) — confirmed the AI assistant was the leak vector.
3. **Triaged PCAPs** in `~/Documents/pcap_dumps/`. Every capture was **198 bytes** except one: `session_4444_dump.pcap` at **2262 bytes** — the attacker's reverse shell session (port 4444 = Metasploit default).
4. **Reassembled the anomalous PCAP** with the AI's tool. The dump contained the attacker's own working notes — including the archive password `westtechvictim1`.
5. **Decrypted** `westtech_projects_encrypted.zip`, decoded the base64 flags file, and used the AI's `liberty_prime` tool to identify the genuine flag among hundreds of decoys.

📄 Full commands and step-by-step terminal output are in the **[PDF writeup](./West_Tech_Writeup.pdf)**.

---

## Flag

```
thm{23,82,20,17,53}
```

---

## Takeaways

- **AI assistants are an attack surface.** A helpful chatbot with broad filesystem access and weak guardrails is functionally a privileged insider with a memory leak.
- **File-size outliers tell stories.** A single 2262-byte capture in a sea of 198-byte placeholders was the entire investigation in one `ls -la`.
- **The attacker's own opsec mistakes** (forgetting that the reverse shell session itself got captured) handed defenders the password.
- **Defence-in-depth matters.** The chain failed because one layer — the AI — was over-trusted and under-restricted.

---

## Repository Layout

```
.
├── README.md                  ← this file (summary)
└── West_Tech_Writeup.pdf      ← full step-by-step walkthrough
```

---

*Writeup by Freedom &middot; MSc Cyber Security, University of Roehampton*
