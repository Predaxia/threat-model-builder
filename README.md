<div align="center">

<img src="https://img.shields.io/badge/PREDAXIA-THREAT%20MODEL%20BUILDER-c0392b?style=for-the-badge&labelColor=0a0a0a" alt="Predaxia Threat Model Builder">

# Threat Model Builder

### A personal threat model in three minutes. Five questions. Zero data collected.

<br>

[![Live](https://img.shields.io/badge/LIVE-predaxia.com-c0392b?style=flat-square&labelColor=0a0a0a)](https://predaxia.com/threat-model-builder/)
[![License](https://img.shields.io/badge/license-MIT-888888?style=flat-square&labelColor=0a0a0a)](LICENSE)
[![Status](https://img.shields.io/badge/status-production-2ecc71?style=flat-square&labelColor=0a0a0a)](https://predaxia.com/threat-model-builder/)
[![No Tracking](https://img.shields.io/badge/tracking-zero-c0392b?style=flat-square&labelColor=0a0a0a)](#privacy-by-design)

<br>

**For journalists, lawyers, NGOs, military families, divorce, high-risk travel — anyone with something to lose.**

<br>

[**→ Try it live**](https://predaxia.com/threat-model-builder/) &nbsp;·&nbsp; [Read the method](https://predaxia.com/how-to-build-threat-model/) &nbsp;·&nbsp; [Glossary](https://predaxia.com/glossary/threat-model/)

</div>

<br>

---

<br>

## Why this exists

Most security advice is generic. *Use a password manager. Enable 2FA. Be careful what you click.* Useful, but not personal. A journalist protecting sources, a lawyer holding privileged communications, a parent in a custody dispute, and a deployed military spouse all face different adversaries — and they all need different priorities.

The **Threat Model Builder** asks five questions. It returns an OPSEC score, the specific vulnerabilities that score reveals, and the exact next step to close each one.

It runs entirely in your browser. No account. No analytics. No telemetry. The page works offline once loaded. Your answers leave nothing behind.

<br>

## What it does

<table>
<tr>
<td width="50%" valign="top">

### The five-step flow

**1.** &nbsp;Pick your profile (7 archetypes)<br>
**2.** &nbsp;Select what you are protecting<br>
**3.** &nbsp;Identify your real adversaries<br>
**4.** &nbsp;Audit your current setup (5 questions)<br>
**5.** &nbsp;Get your score, gaps, and action plan

</td>
<td width="50%" valign="top">

### What you get back

· OPSEC score `0–100` with severity tier<br>
· Vulnerabilities ranked `high` / `medium`<br>
· Direct link to the fix for each gap<br>
· A printable / copyable report<br>
· Tools tested and verified by Predaxia

</td>
</tr>
</table>

<br>

## Profiles covered

| Profile | Primary threat surface |
|---|---|
| **Journalist** | Source protection · hostile environments |
| **Lawyer / Notary** | Client data · legal confidentiality |
| **NGO / Expat** | Field security · border crossings |
| **Military Family** | Location · deployment OPSEC |
| **Divorce / Legal** | Device audits · evidence protection |
| **High-Risk Travel** | Border agents · hostile networks |
| **Anyone** | Data brokers · mass surveillance · digital hygiene |

<br>

## Scoring model

The score is computed from **five setup answers** and weighted by the **highest-severity adversary** in your profile.

| Question | Range |
|---|---|
| Messaging | `0–3` |
| VPN | `0–3` |
| Passwords | `0–3` |
| Two-factor authentication | `0–3` |
| Data broker exposure | `0–3` |
| **Adversary severity bonus** | `+2 if any selected adversary has severity 3` |

**Final score** = `100 − (raw_points / 15) × 100`, floor 0.

| Score | Tier | Meaning |
|---|---|---|
| `70–100` | <span style="color:#2ecc71">**SOLID**</span> | Optimizations, not emergencies |
| `40–69` | <span style="color:#d4a017">**EXPOSED**</span> | Exploitable gaps your adversaries can use |
| `0–39` | <span style="color:#c0392b">**CRITICAL**</span> | Setup leaves you compromised in real operations |

<br>

## Privacy by design

```
┌──────────────────────────────────────────────────────┐
│  No account.            No email.        No cookies. │
│  No analytics.          No telemetry.    No CDN.     │
│  No server-side state.  No localStorage. No tracking.│
└──────────────────────────────────────────────────────┘
```

Every answer stays in browser memory until you reload the page. The promise of zero storage is incompatible with persistence. If you want to keep your result, **copy it** or **print it** from the result screen.

<br>

## Run locally

```bash
git clone https://github.com/Predaxia/threat-model-builder.git
cd threat-model-builder
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

That's it. No build step. No dependencies. Single HTML file with vanilla JavaScript and inline CSS. Open it from a USB key, host it on a static folder, mirror it as a Tor hidden service — it does not care.

<br>

## Embed it

Drop a single iframe wherever you need it.

```html
<iframe
  src="https://predaxia.com/threat-model-builder/"
  width="100%" height="900"
  frameborder="0"
  title="Threat Model Builder">
</iframe>
```

Or self-host: `index.html` is fully standalone.

<br>

## Stack

| Layer | Choice | Why |
|---|---|---|
| Markup | Hand-written HTML5 | One file. Zero magic. |
| Styling | Inline CSS, custom properties | No framework. No CDN call. |
| Logic | Vanilla JS (IIFE, no deps) | Runs offline. No supply chain. |
| Fonts | Space Grotesk + Inter (Google Fonts) | Optional. Falls back to system. |
| Icons | Inline SVG (Lucide-style) | No icon font. ASCII-safe. |
| Schema | JSON-LD (`HowTo`, `FAQPage`) | Structured data for search. |

<br>

## Project structure

```
threat-model-builder/
├── index.html       Standalone wizard (HTML + CSS + JS, single file)
├── README.md        This file
└── LICENSE          MIT
```

<br>

## Roadmap

- [ ] Multi-language support (FR / ES / DE / AR)
- [ ] Profile: activist
- [ ] Profile: domestic abuse survivor (with safeguards)
- [ ] Exportable PDF report (client-side)
- [ ] Adversary database with country-specific overlays
- [ ] CLI version for the paranoid

Suggestions are read. Open an issue.

<br>

## Contributing

This is a public mirror of the production tool running on [predaxia.com](https://predaxia.com/threat-model-builder/). Contributions are welcome but kept narrow:

- **Yes** — typo fixes, accessibility improvements, clearer copy, better SVG icons, additional profiles backed by a real-world threat surface
- **No** — analytics, third-party scripts, dependency on external services, "AI-powered" anything, dark patterns, growth hacks
- **Maybe** — translations (open an issue first so we can sync vocabulary)

Open a Pull Request from a fork. Keep changes minimal and focused. The single-file constraint is non-negotiable.

<br>

## Security disclosure

Found a bug that affects user safety? Email **security@predaxia.com** with details. PGP key on the website. Please do not open public issues for security-sensitive findings.

<br>

## About Predaxia

> Predaxia is an independent OPSEC publication. We test the tools we recommend, refuse the tools we don't, and never accept payment for placement. Affiliate links exist on the main site and are flagged accordingly. This repository is part of our commitment to put the operational layer in everyone's hands.

[predaxia.com](https://predaxia.com) &nbsp;·&nbsp; [Newsletter](https://predaxia.com/newsletter/) &nbsp;·&nbsp; [Glossary](https://predaxia.com/glossary/)

<br>

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, host it, modify it, ship it. Attribution appreciated, not required.

<br>

---

<div align="center">

<sub>**There is no perfect setup.<br>The goal is simple: make yourself a harder target than the person next to you.**</sub>

<br><br>

<sub>Built with care in the EU · No trackers were harmed in the making of this tool</sub>

</div>
