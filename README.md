# Threat Model Builder

Interactive threat model builder for civilians. 5 questions, personalized security score, actionable recommendations.

**Live version:** [predaxia.com/threat-model-builder](https://predaxia.com/threat-model-builder/)

## What it does

Most threat model guides are 30-page PDFs. Nobody finishes them. This tool asks 5 questions and gives you a personalized security assessment in 3 minutes.

## Features

- **7 profiles:** journalist, lawyer, NGO/expat, military family, divorce/legal, high-risk travel, anyone
- **Adversary severity scoring** with dot indicators (1-3)
- **Current setup assessment:** messaging, VPN, passwords, 2FA, device separation
- **Score 0-100** with identified vulnerabilities and specific recommendations
- **Zero data collected** — runs entirely in the browser
- **Single HTML file** — no dependencies, no build step, no framework

## How it works

1. **Who are you?** — Select your profile
2. **What are you protecting?** — Select your assets
3. **Who are you protecting against?** — Select adversaries (with severity ratings)
4. **Current setup?** — Answer honestly about your tools
5. **Results** — Score, vulnerabilities, and recommended reading

The scoring penalizes weak setups (SMS-only messaging, free VPNs, no password manager, SMS 2FA, single device) and factors in adversary severity. A max-severity adversary (state surveillance, armed groups) adds penalty points.

## Scoring

| Score | Level | Meaning |
|-------|-------|---------|
| 70-100 | SOLID | No critical gaps. Stay maintained. |
| 40-69 | EXPOSED | Exploitable gaps identified. |
| 0-39 | CRITICAL | Immediate action needed. |

## Run it

Open `index.html` in a browser. That's it.

Or serve it:

```
python3 -m http.server 8000
```

## Contributing

- **Add a profile:** Add entries to the `P`, `AS`, `ADV`, and `ART` arrays in the script
- **Fix scoring:** Edit the `SC` object and `comp()` function
- **Add articles:** Edit the `ART` object with `{t: "title", u: "/slug/"}`
- **Report issues:** Open an issue

## License

MIT — see [LICENSE](LICENSE)

## About

Built by [Predaxia](https://predaxia.com) — privacy for people who have something to lose.
