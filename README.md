# Secure by Design — Statement of Applicability Generator

A free, unbranded tool for producing a **Secure by Design Statement of Applicability (SoA)** for any software development project, based on the data classifications you handle, the stakeholders you serve, the technologies you use, and the data protection and privacy laws that apply.

Hosted at **https://sbd.govassure.uk**

## What it does

- Walks a delivery team through six steps: project details, data classifications, stakeholders, technologies, control selection and risk capture, review and export.
- Filters the full **Secure Controls Framework (SCF) 2026.1** library — all 1,468 controls across 33 domains — down to what is applicable to your scope.
- Starts from a curated baseline of 75 high-priority controls, each mapped to **UK Government Secure by Design principles**, **NCSC Cyber Assessment Framework (CAF) v4.0** outcomes, relevant threats and applicable legislation.
- Maps applicability to UK and EU law: UK GDPR, EU GDPR, Data Protection Act 2018, PECR, NIS Regulations 2018, EU NIS2, the EU AI Act, DORA, the Computer Misuse Act 1990, FOIA, the Equality Act 2010 and the Human Rights Act 1998.
- Exports the completed SoA, including per-control inclusion decisions, justifications and risk assessments.

## Privacy

The tool is a single self-contained HTML page. It makes **no network requests** — there is no backend, no analytics and no cookies. All responses are stored in your browser's localStorage only and never leave your device. The deployment enforces a strict Content Security Policy (`default-src 'none'`) so the page cannot call out even if modified.

## Deployment

Static single-file site. On Vercel: import this repo, framework preset **Other**, no build command. Security headers are set in `vercel.json`.

## Architecture

| File | Purpose |
| --- | --- |
| `index.html` | The entire application — UI, control data and logic in one file |
| `vercel.json` | Hosting configuration: security headers, caching |

Within `index.html`, the key data structures are `SBD_PRINCIPLES`, `CAF_OUTCOMES`, `DATA_TYPES`, `STAKEHOLDERS`, `TECHNOLOGIES`, `LEGISLATION`, `DOMAIN_RULES` (domain-level applicability gating), `BASELINE` (the 75 curated controls) and `SCF_DATA` (the full SCF library, stored compactly).

## Reference frameworks

- [UK Government Secure by Design](https://www.security.gov.uk/policy-and-guidance/secure-by-design/)
- [NCSC Cyber Assessment Framework v4.0](https://www.ncsc.gov.uk/collection/cyber-assessment-framework)
- [Secure Controls Framework (SCF) 2026.1](https://securecontrolsframework.com/)

## Licensing and attribution

The Secure Controls Framework content embedded in this tool is © Secure Controls Framework Council, LLC and is redistributed under the [Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)](https://creativecommons.org/licenses/by-nd/4.0/) licence. NCSC CAF and UK Government Secure by Design materials are used under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).

This tool is not affiliated with or endorsed by GOV.UK, the NCSC or the Secure Controls Framework Council. It does not constitute legal advice — confirm applicable legal obligations with your data protection and legal advisers.
