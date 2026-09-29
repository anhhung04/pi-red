![claude-red banner](/assets/banner.png)

<div align="center">

# pi-red

**Offensive security skills for pi — drop-in `SKILL.md` files that turn pi into a context-aware red team operator.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-79-red.svg)](#skill-index)
[![Categories](https://img.shields.io/badge/categories-23-orange.svg)](#categories)
[![Stars](https://img.shields.io/github/stars/SnailSploit/claude-red?style=social)](https://github.com/SnailSploit/claude-red)
[![Forks](https://img.shields.io/github/forks/SnailSploit/claude-red?style=social)](https://github.com/SnailSploit/claude-red/network/members)

[Overview](#overview) &bull; [Quickstart](#quickstart) &bull; [Categories](#categories) &bull; [Skill Index](#skill-index) &bull; [Roadmap](#roadmap) &bull; [Contributing](#contributing)

</div>

---

## Overview

`pi-red` is a curated library of offensive security skills for pi. Each skill is a structured `SKILL.md` file that primes pi with expert-level methodology for a specific attack surface — from SQL injection to shellcode, EDR evasion to ADCS abuse.

Drop a skill into your pi environment and it behaves like a domain specialist: it knows the techniques, the tooling, the edge cases, and the escalation paths. Skills load on demand based on conversational triggers — you don't pay context for skills you aren't using.

**Use cases:** authorized red team engagements, bug bounty triage, security research, CTF preparation, operator training, and methodical attack surface exploration.

**for our actual research using skills -> https://snailsploit.com**
---

## Quickstart

### omp marketplace

```bash
omp plugin marketplace add SnailSploit/pi-red
omp plugin install offensive-web@pi-red                              # one category
omp plugin install offensive-web@pi-red offensive-wireless@pi-red    # multiple
```

Or in the TUI: `/marketplace add SnailSploit/pi-red`, then `/marketplace` to browse and install interactively. For a local checkout: `omp plugin marketplace add ./pi-red`.

Skills load on demand from conversational triggers; invoke one explicitly with `/skill:offensive-sqli` (requires skill commands enabled).

---

## Categories

| Category | Skills | Focus |
|---|---:|---|
| [Web Application](#web-application) | 16 | OWASP Top 10, business logic, advanced web vulnerability classes |
| [Auth & Identity](#auth--identity) | 2 | JWT exploitation, OAuth/OIDC abuse |
| [Active Directory](#active-directory) | 2 | On-prem AD attack methodology |
| [Wireless](#wireless) | 14 | 802.11, WPA2/3, EAP, WPS, evil-twin, BLE, Zigbee, Z-Wave, LoRa, sub-GHz |
| [Cloud](#cloud) | 1 | AWS, Azure, GCP attack paths |
| [Mobile](#mobile) | 1 | Android and iOS application testing |
| [IoT & Embedded](#iot--embedded) | 1 | Hardware, firmware, RTOS, ICS/OT |
| [Infrastructure & Red Team](#infrastructure--red-team) | 7 | Initial access, EDR evasion, advanced red team operations, Windows internals |
| [Exploit Development](#exploit-development) | 6 | Stack/heap corruption, ROP, mitigations, crash analysis, TOCTOU |
| [Fuzzing & Vulnerability Research](#fuzzing--vulnerability-research) | 4 | libFuzzer, AFL++, coverage-guided fuzzing, vulnerability taxonomy |
| [Reconnaissance](#reconnaissance) | 2 | OSINT tooling and structured intelligence collection |
| [API Security](#api-security) | 2 | REST/gRPC/WebSocket testing, business logic abuse |
| [Container & Kubernetes](#container--kubernetes) | 2 | Container escape, Kubernetes cluster exploitation |
| [CI/CD & Pipeline](#cicd--pipeline) | 2 | Pipeline exploitation, secrets extraction |
| [Cryptography](#cryptography) | 2 | Cryptographic implementation attacks, TLS/SSL |
| [Privilege Escalation](#privilege-escalation) | 2 | Linux and Windows privilege escalation |
| [Post-Exploitation](#post-exploitation) | 3 | Lateral movement, persistence mechanisms, data exfiltration |
| [Forensics & C2](#forensics--c2) | 2 | Anti-forensics tradecraft, C2 framework operations |
| [Supply Chain](#supply-chain) | 2 | Supply chain attacks, dependency confusion |
| [Social Engineering](#social-engineering) | 2 | Phishing campaigns, physical/vishing/smishing |
| [Network Attacks](#network-attacks) | 1 | Layer 2/3 attacks, MITM, protocol poisoning |
| [AI Security](#ai-security) | 1 | Prompt injection, jailbreaking, RAG poisoning |
| [Utility](#utility) | 2 | Fast triage checklists, professional reporting |

---

## Skill Index

### Web Application

`plugins/web/skills/`

| Skill | Description |
|---|---|
| [`offensive-sqli`](plugins/web/skills/offensive-sqli/SKILL.md) | SQL injection — error-based, blind, OOB, DB-specific payloads, ORM CVEs |
| [`offensive-xss`](plugins/web/skills/offensive-xss/SKILL.md) | Cross-site scripting — stored, reflected, DOM-based, mutation XSS |
| [`offensive-ssrf`](plugins/web/skills/offensive-ssrf/SKILL.md) | Server-side request forgery — cloud metadata pivots, filter bypass |
| [`offensive-ssti`](plugins/web/skills/offensive-ssti/SKILL.md) | Server-side template injection — engine fingerprinting, RCE chains |
| [`offensive-xxe`](plugins/web/skills/offensive-xxe/SKILL.md) | XML external entity — OOB exfiltration, blind XXE techniques |
| [`offensive-idor`](plugins/web/skills/offensive-idor/SKILL.md) | Insecure direct object references — enumeration, authorization bypass |
| [`offensive-file-upload`](plugins/web/skills/offensive-file-upload/SKILL.md) | File upload — extension bypass, polyglot files, webshell deployment |
| [`offensive-rce`](plugins/web/skills/offensive-rce/SKILL.md) | Remote code execution — command injection, deserialization chains |
| [`offensive-deserialization`](plugins/web/skills/offensive-deserialization/SKILL.md) | Insecure deserialization — Java, PHP, .NET gadget chains |
| [`offensive-race-condition`](plugins/web/skills/offensive-race-condition/SKILL.md) | Race conditions — TOCTOU, single-packet attacks, limit bypass |
| [`offensive-request-smuggling`](plugins/web/skills/offensive-request-smuggling/SKILL.md) | HTTP request smuggling — CL.TE, TE.CL, H2 desync |
| [`offensive-open-redirect`](plugins/web/skills/offensive-open-redirect/SKILL.md) | Open redirect — OAuth token theft, phishing, SSRF pivots |
| [`offensive-parameter-pollution`](plugins/web/skills/offensive-parameter-pollution/SKILL.md) | HTTP parameter pollution — WAF bypass, logic confusion |
| [`offensive-graphql`](plugins/web/skills/offensive-graphql/SKILL.md) | GraphQL — introspection abuse, batching attacks, alias-based IDOR |
| [`offensive-waf-bypass`](plugins/web/skills/offensive-waf-bypass/SKILL.md) | WAF bypass — encoding tricks, chunked transfer, case mutation |
| [`offensive-business-logic`](plugins/web/skills/offensive-business-logic/SKILL.md) | Business logic — workflow bypass, pricing abuse, multi-step chains |

### Auth & Identity

`plugins/auth/skills/`

| Skill | Description |
|---|---|
| [`offensive-jwt`](plugins/auth/skills/offensive-jwt/SKILL.md) | JWT attacks — alg:none, key confusion, secret cracking, claim tampering |
| [`offensive-oauth`](plugins/auth/skills/offensive-oauth/SKILL.md) | OAuth/OIDC — redirect URI abuse, token leakage, PKCE bypass |

### Active Directory

`plugins/active-directory/skills/`

| Skill | Description |
|---|---|
| [`offensive-active-directory`](plugins/active-directory/skills/offensive-active-directory/SKILL.md) | AD methodology — Kerberoast, ASREProast, ACL abuse, ADCS ESC1-15, delegation, hybrid AAD |
| [`offensive-netexec`](plugins/active-directory/skills/offensive-netexec/SKILL.md) | NetExec (nxc) — network exploitation and post-exploitation for AD environments |

### Wireless

`plugins/wireless/skills/`

| Skill | Description |
|---|---|
| [`offensive-wifi`](plugins/wireless/skills/offensive-wifi/SKILL.md) | 802.11 overview — entrypoint for wireless assessments |
| [`offensive-wifi-recon`](plugins/wireless/skills/offensive-wifi-recon/SKILL.md) | Adapter configuration, monitor mode, multi-band airspace mapping |
| [`offensive-wpa2-psk`](plugins/wireless/skills/offensive-wpa2-psk/SKILL.md) | WPA2-PSK — handshake capture, PMKID extraction, hashcat cracking |
| [`offensive-wpa3-sae`](plugins/wireless/skills/offensive-wpa3-sae/SKILL.md) | WPA3-SAE — transition-mode downgrade, Dragonblood, side-channel attacks |
| [`offensive-wpa-enterprise`](plugins/wireless/skills/offensive-wpa-enterprise/SKILL.md) | 802.1X/EAP — credential relay, evil-twin RADIUS, certificate abuse |
| [`offensive-wps`](plugins/wireless/skills/offensive-wps/SKILL.md) | WPS — Pixie Dust offline attack, online PIN brute force, vendor PIN prediction |
| [`offensive-evil-twin`](plugins/wireless/skills/offensive-evil-twin/SKILL.md) | Evil twin — KARMA, Mana, captive portal credential capture, MITM |
| [`offensive-krack-fragattacks`](plugins/wireless/skills/offensive-krack-fragattacks/SKILL.md) | KRACK and FragAttacks — supplicant vulnerability testing |
| [`offensive-deauth-disassoc`](plugins/wireless/skills/offensive-deauth-disassoc/SKILL.md) | Deauthentication — targeted/broadcast frames, PMF awareness |
| [`offensive-bluetooth-ble`](plugins/wireless/skills/offensive-bluetooth-ble/SKILL.md) | Bluetooth LE — GATT enumeration, pairing downgrade, sniffing, MITM |
| [`offensive-bluetooth-classic`](plugins/wireless/skills/offensive-bluetooth-classic/SKILL.md) | Bluetooth BR/EDR — SDP probing, KNOB attack, BlueBorne, HID spoofing |
| [`offensive-zigbee-thread-matter`](plugins/wireless/skills/offensive-zigbee-thread-matter/SKILL.md) | 802.15.4 mesh — KillerBee, Touchlink commissioning abuse, ZCL injection |
| [`offensive-z-wave`](plugins/wireless/skills/offensive-z-wave/SKILL.md) | Z-Wave — S0 key derivation, S2 commissioning attacks, hub pivots |
| [`offensive-lorawan-sub-ghz`](plugins/wireless/skills/offensive-lorawan-sub-ghz/SKILL.md) | LoRaWAN and sub-GHz — ABP/OTAA attacks, KeeLoq, fixed-code replay, TPMS |

### Cloud

`plugins/cloud/skills/`

| Skill | Description |
|---|---|
| [`offensive-cloud`](plugins/cloud/skills/offensive-cloud/SKILL.md) | Multi-cloud — privilege escalation, IMDS abuse, cross-account pivots, CSPM evasion |

### Mobile

`plugins/mobile/skills/`

| Skill | Description |
|---|---|
| [`offensive-mobile`](plugins/mobile/skills/offensive-mobile/SKILL.md) | Android and iOS — Frida hooking, certificate pinning bypass, storage, biometric flaws |

### IoT & Embedded

`plugins/iot/skills/`

| Skill | Description |
|---|---|
| [`offensive-iot`](plugins/iot/skills/offensive-iot/SKILL.md) | IoT/OT — hardware interfaces, firmware extraction, RTOS, ICS protocols, MQTT/CoAP |

### Infrastructure & Red Team

`plugins/infrastructure/skills/`

| Skill | Description |
|---|---|
| [`offensive-initial-access`](plugins/infrastructure/skills/offensive-initial-access/SKILL.md) | Initial access — phishing payloads, drive-by delivery, supply chain vectors (TA0001) |
| [`offensive-advanced-redteam`](plugins/infrastructure/skills/offensive-advanced-redteam/SKILL.md) | Full kill chain — C2 infrastructure, OPSEC, lateral movement, persistence |
| [`offensive-edr-evasion`](plugins/infrastructure/skills/offensive-edr-evasion/SKILL.md) | EDR evasion — userland unhooking, indirect syscalls, PPID spoofing |
| [`offensive-shellcode`](plugins/infrastructure/skills/offensive-shellcode/SKILL.md) | Shellcode — writing, encoding, injection techniques, position-independent code |
| [`offensive-keylogger-arch`](plugins/infrastructure/skills/offensive-keylogger-arch/SKILL.md) | Input capture — keylogger architecture, hooking mechanisms |
| [`offensive-windows-mitigations`](plugins/infrastructure/skills/offensive-windows-mitigations/SKILL.md) | Windows mitigations — ACG, CIG, CFG, CET bypass techniques |
| [`offensive-windows-boundaries`](plugins/infrastructure/skills/offensive-windows-boundaries/SKILL.md) | Windows boundary defeat — sandbox escape, integrity level bypass |

### Exploit Development

`plugins/exploit-dev/skills/`

| Skill | Description |
|---|---|
| [`offensive-exploit-development`](plugins/exploit-dev/skills/offensive-exploit-development/SKILL.md) | Exploit development — stack/heap corruption, ROP chains, mitigation bypass |
| [`offensive-exploit-dev-course`](plugins/exploit-dev/skills/offensive-exploit-dev-course/SKILL.md) | Structured exploit development curriculum |
| [`offensive-basic-exploitation`](plugins/exploit-dev/skills/offensive-basic-exploitation/SKILL.md) | Linux binary exploitation — beginner to intermediate, mitigations disabled |
| [`offensive-crash-analysis`](plugins/exploit-dev/skills/offensive-crash-analysis/SKILL.md) | Crash triage — exploitability assessment, root-cause analysis |
| [`offensive-mitigations`](plugins/exploit-dev/skills/offensive-mitigations/SKILL.md) | Modern mitigations — ASLR, CFG, CET, PAC analysis and bypass |
| [`offensive-toctou`](plugins/exploit-dev/skills/offensive-toctou/SKILL.md) | TOCTOU race conditions — binary, kernel, web, and container contexts |

### Fuzzing & Vulnerability Research

`plugins/fuzzing/skills/`

| Skill | Description |
|---|---|
| [`offensive-fuzzing`](plugins/fuzzing/skills/offensive-fuzzing/SKILL.md) | Fuzzing — libFuzzer, AFL++, coverage-guided strategies, mutation engines |
| [`offensive-fuzzing-course`](plugins/fuzzing/skills/offensive-fuzzing-course/SKILL.md) | Vulnerability discovery through fuzzing — structured curriculum |
| [`offensive-bug-identification`](plugins/fuzzing/skills/offensive-bug-identification/SKILL.md) | Bug identification — code review patterns, static analysis triggers |
| [`offensive-vuln-classes`](plugins/fuzzing/skills/offensive-vuln-classes/SKILL.md) | Vulnerability taxonomy — real-world examples, classification frameworks |

### Reconnaissance

`plugins/recon/skills/`

| Skill | Description |
|---|---|
| [`offensive-osint`](plugins/recon/skills/offensive-osint/SKILL.md) | OSINT tooling — recon-ng, theHarvester, Maltego, Spiderfoot |
| [`offensive-osint-methodology`](plugins/recon/skills/offensive-osint-methodology/SKILL.md) | OSINT methodology — structured intelligence collection and analysis |

### API Security

`plugins/api/skills/`

| Skill | Description |
|---|---|
| [`offensive-api-security`](plugins/api/skills/offensive-api-security/SKILL.md) | API testing — OWASP API Top 10, BOLA, BFLA, mass assignment, rate limiting |
| [`offensive-api-abuse`](plugins/api/skills/offensive-api-abuse/SKILL.md) | API business logic — endpoint chaining, batching abuse, webhook hijacking |

### Container & Kubernetes

`plugins/container/skills/`

| Skill | Description |
|---|---|
| [`offensive-container-escape`](plugins/container/skills/offensive-container-escape/SKILL.md) | Container breakout — privileged mode, Docker socket, capabilities, runc CVEs |
| [`offensive-k8s-attacks`](plugins/container/skills/offensive-k8s-attacks/SKILL.md) | Kubernetes attacks — RBAC abuse, etcd access, kubelet API, pod escape, CRD exploitation |

### CI/CD & Pipeline

`plugins/cicd/skills/`

| Skill | Description |
|---|---|
| [`offensive-cicd-pipeline`](plugins/cicd/skills/offensive-cicd-pipeline/SKILL.md) | CI/CD exploitation — GitHub Actions injection, Jenkins RCE, GitLab CI abuse |
| [`offensive-cicd-secrets`](plugins/cicd/skills/offensive-cicd-secrets/SKILL.md) | CI/CD secrets — environment variable extraction, vault misconfigs, runner token abuse |

### Cryptography

`plugins/crypto/skills/`

| Skill | Description |
|---|---|
| [`offensive-crypto-attacks`](plugins/crypto/skills/offensive-crypto-attacks/SKILL.md) | Cryptographic attacks — padding oracle, ECB manipulation, hash extension, weak PRNG |
| [`offensive-tls-attacks`](plugins/crypto/skills/offensive-tls-attacks/SKILL.md) | TLS/SSL attacks — POODLE, DROWN, Heartbleed, pinning bypass, 0-RTT replay |

### Privilege Escalation

`plugins/privesc/skills/`

| Skill | Description |
|---|---|
| [`offensive-linux-privesc`](plugins/privesc/skills/offensive-linux-privesc/SKILL.md) | Linux privilege escalation — SUID, capabilities, sudo, cron, kernel exploits |
| [`offensive-windows-privesc`](plugins/privesc/skills/offensive-windows-privesc/SKILL.md) | Windows privilege escalation — Potato family, service misconfigs, DLL hijacking, UAC bypass |

### Post-Exploitation

`plugins/post-exploitation/skills/`

| Skill | Description |
|---|---|
| [`offensive-lateral-movement`](plugins/post-exploitation/skills/offensive-lateral-movement/SKILL.md) | Lateral movement — PTH, PTT, NTLM relay, WMI/WinRM/DCOM, tunneling |
| [`offensive-persistence`](plugins/post-exploitation/skills/offensive-persistence/SKILL.md) | Persistence — registry, scheduled tasks, WMI subscriptions, ticket forgery, PAM backdoors |
| [`offensive-data-exfiltration`](plugins/post-exploitation/skills/offensive-data-exfiltration/SKILL.md) | Data exfiltration — DNS/HTTPS/ICMP tunneling, cloud staging, steganography |

### Forensics & C2

`plugins/forensics/skills/`

| Skill | Description |
|---|---|
| [`offensive-anti-forensics`](plugins/forensics/skills/offensive-anti-forensics/SKILL.md) | Anti-forensics — log manipulation, timestomping, ADS abuse, memory cleanup |
| [`offensive-c2-frameworks`](plugins/forensics/skills/offensive-c2-frameworks/SKILL.md) | C2 tradecraft — Cobalt Strike, Sliver, Mythic, Havoc, redirectors, domain fronting |

### Supply Chain

`plugins/supply-chain/skills/`

| Skill | Description |
|---|---|
| [`offensive-supply-chain`](plugins/supply-chain/skills/offensive-supply-chain/SKILL.md) | Supply chain attacks — dependency confusion, typosquatting, build system compromise |
| [`offensive-dependency-confusion`](plugins/supply-chain/skills/offensive-dependency-confusion/SKILL.md) | Dependency confusion — npm/PyPI/NuGet/Maven namespace attacks, safe PoC methodology |

### Social Engineering

`plugins/social-engineering/skills/`

| Skill | Description |
|---|---|
| [`offensive-phishing`](plugins/social-engineering/skills/offensive-phishing/SKILL.md) | Phishing — GoPhish, EvilGinx2, payload delivery, email authentication bypass |
| [`offensive-social-engineering`](plugins/social-engineering/skills/offensive-social-engineering/SKILL.md) | Social engineering — pretexting, vishing, smishing, physical SE, USB drops |

### Network Attacks

`plugins/network/skills/`

| Skill | Description |
|---|---|
| [`offensive-network-attacks`](plugins/network/skills/offensive-network-attacks/SKILL.md) | Network layer attacks — ARP spoofing, LLMNR/NBT-NS poisoning, VLAN hopping, MITM |

### AI Security

`plugins/ai/skills/`

| Skill | Description |
|---|---|
| [`offensive-ai-security`](plugins/ai/skills/offensive-ai-security/SKILL.md) | AI/ML security — prompt injection, jailbreaking, RAG poisoning, model extraction |

### Utility

`plugins/utility/skills/`

| Skill | Description |
|---|---|
| [`offensive-fast-checking`](plugins/utility/skills/offensive-fast-checking/SKILL.md) | Fast triage — quick-win identification checklists |
| [`offensive-reporting`](plugins/utility/skills/offensive-reporting/SKILL.md) | Professional reporting — CVSS scoring, evidence standards, executive summaries |

---

## Roadmap

The library is being expanded across multiple phases. See [CHANGELOG.md](CHANGELOG.md) for release history.

| Phase | Focus | Skills | Status |
|---|---|---:|---|
| 1 | Internal AD/Windows — split into focused skills | +16 | Planned |
| 2 | Cloud Identity — Entra, ADFS, Okta, M365 | +10 | Planned |
| 3 | Wireless — WPA2/3, EAP, BLE, Zigbee, Z-Wave, LoRa, sub-GHz | +12 | Complete |
| 4 | IoT — UART/JTAG, flash extraction, fault injection, RTOS, ICS | +10 | Planned |
| 5 | Web Fundamentals — recon, auth bypass, access control, CSRF, CORS | +8 | Planned |
| 6 | Web Advanced — proto pollution, SAML, OIDC, WebSocket, SSI/ESI | +10 | Planned |
| 7 | Documentation and tooling polish | — | Complete |
| 8 | New categories — 10 new domains with 20 skills | +20 | Complete |
| 9 | Deep rewrites — deserialization, GraphQL, advanced red team, SSTI | — | Complete |

Target: ~130 skills across 23+ categories.

---

## Contributing

Contributions welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the skill template, frontmatter standard, and review process. Focused, single-surface skills are preferred over monolithic overviews.

## License

[MIT](LICENSE) — use freely, attribution appreciated.

## Acknowledgements

- **Author:** [Kai Aizen](https://snailsploit.com) (SnailSploit) — GenAI security research
- **Original Checklists:** [Sahar Shlichov](https://github.com/sahar042/offensive-checklist) — the offensive checklist collection that many of these skills build on
- **Community:** Pull requests and feedback that keep the library aligned with the evolving threat landscape

---

<div align="center">

*Give pi the right skill and it stops being a chatbot — it becomes an operator.*

[snailsploit.com](https://snailsploit.com) &bull; [GitHub](https://github.com/SnailSploit) &bull; [Research](https://snailsploit.com/research) &bull; [X](https://x.com/SnailSploit)

</div>
