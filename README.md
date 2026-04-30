# Tele-Care Connect

> An open-source telemedicine platform that brings doctors closer to patients in underserved communities.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![SDG 3](https://img.shields.io/badge/SDG-3%20Good%20Health%20%26%20Well--being-green.svg)](https://sdgs.un.org/goals/goal3)
[![DPG-aligned](https://img.shields.io/badge/DPG-aligned-blue.svg)](https://digitalpublicgoods.net/standard/)
[![Status](https://img.shields.io/badge/status-prototype-orange.svg)](#)

**Live demo:** https://arman300s.github.io/tele-care-connect/

---

## 1. Project Description

Tele-Care Connect is a lightweight, web-based telemedicine platform designed for patients and small clinics that cannot access or afford commercial closed-source telehealth services. It lets a patient browse available doctors, book a consultation, join a video call, and download a written summary of the consultation. A doctor can manage their schedule and attach prescriptions or notes.

The project is intentionally simple, free, and locally adaptable: anyone can fork it, translate it, host it, or extend it.

---

## 2. The Problem and Our Solution

**Problem.** Patients in rural and semi-urban areas of Central Asia spend hours travelling for short consultations. Small private clinics cannot afford the per-seat fees of commercial telehealth platforms. Existing open-source health platforms (OpenMRS, Bahmni) are excellent for hospitals but heavy for a single doctor or NGO.

**Solution.** A small, lightweight, MIT-licensed web application that:

- runs as a static front-end on any host (GitHub Pages, Netlify, on-premise);
- has an optional Node.js + SQLite backend for clinics that need persistence;
- uses Jitsi Meet (also open source) for the video layer, so we keep the openness chain unbroken;
- ships with a portable patient summary that the patient owns and can export as JSON or PDF.

---

## 3. SDG Alignment

The project is primarily aligned with **SDG 3 — Good Health and Well-being**, in particular:

- **Target 3.8** Universal health coverage and access to quality essential healthcare services.
- **Target 3.d** Strengthen capacity for early warning, risk reduction and management of health risks.

Secondary alignment: **SDG 10** (Reduced Inequalities) and **SDG 9** (Industry, Innovation, Infrastructure).

---

## 4. How to Use the Project

### Option A — Try the live demo (no install)

Open https://arman300s.github.io/tele-care-connect/ in any modern browser. No login is required for the demo.

### Option B — Run the static front-end locally

```bash
git clone https://github.com/arman300s/tele-care-connect.git
cd tele-care-connect/frontend
# Serve with any static server, e.g.:
python3 -m http.server 8080
# Then open http://localhost:8080
```

### Option C — Run with the optional backend (self-hosting)

```bash
cd tele-care-connect/backend
npm install
npm run dev
# API available on http://localhost:3000
```

The backend uses a local SQLite file by default; no external database is required for development.

---

## 5. How to Contribute

We welcome contributions from anyone — code, documentation, translations or bug reports. The full guide is in [CONTRIBUTING.md](./CONTRIBUTING.md). In short:

1. Fork the repository.
2. Create a branch named `feature/<short-description>` or `docs/<short-description>`.
3. Make small, focused commits using [Conventional Commits](https://www.conventionalcommits.org/) (e.g. `feat(frontend): add doctor list filter`).
4. Open a pull request against `main`. Fill in the PR template; at least one maintainer review is required.

By contributing you agree to follow our [Code of Conduct](./CODE_OF_CONDUCT.md).

---

## 6. License

This project is released under the **MIT License** — see [LICENSE](./LICENSE) for the full text.

We chose MIT because it is permissive (small clinics and NGOs can integrate it into their internal tools without legal friction), short and easy to read, OSI-approved, and accepted by the Digital Public Goods Alliance. Trade-off: a closed fork is legally possible; we accept this risk in exchange for broader adoption.

---

## 7. Documentation

Additional documentation lives in the [`/docs`](./docs) folder:

- `architecture.md` — high-level architecture and data flow.
- `dpg-assessment.md` — our self-assessment against the 9 DPG indicators.
- `user-guide.pdf` — short patient and doctor guide.
- `figma-export.pdf` — exported high-fidelity prototype.

---

## 8. Privacy and Security

Tele-Care Connect follows a privacy-by-design approach:

- We collect the **minimum** information required for the consultation.
- All data is transmitted over HTTPS.
- The optional backend stores data encrypted at rest.
- The patient owns their consultation history and can export or delete it at any time.
- We align with the Republic of Kazakhstan's Law on Personal Data and with GDPR principles.

Security issues should be reported privately by email to the maintainers (see `SECURITY.md`).

---

## 9. Team Members and Roles

| Member | Role | Main Responsibilities |
|---|---|---|
| **Shoibek Arman** | Project Lead / Repo Owner | Repository, GitHub Pages deployment, license, DPG self-assessment, code reviews. |
| **Mereke Nuray** | Frontend Developer | Patient-facing UI, booking flow, responsive layout, accessibility. |
| **Muktar Riana** | UX / Prototype Designer | Figma wireframes and high-fidelity prototype, design system. |
| **Baudinov Alisher** | Documentation & DPG Compliance | README, CONTRIBUTING, Code of Conduct, DPG mapping, privacy section. |
| **Balseit Yeldana** | Research & Report Author | Problem research, SDG alignment, SWOT, competitor analysis, final report. |

---

## 10. Roadmap

- [ ] Internationalisation (Kazakh, Russian).
- [ ] Automated tests (Jest for backend, Playwright for frontend).
- [ ] OpenAPI specification for the backend.
- [ ] Submission to the [Digital Public Goods Alliance registry](https://digitalpublicgoods.net/registry/).
- [ ] Mobile-friendly PWA installation flow.

---

## 11. Acknowledgements

This project was built as part of the *Introduction to Open Source Development* course (DPG Track), supported by UNICEF Office of Innovation, UNU-MERIT, Maastricht University and KBTU. We thank our instructors and the open-source community whose work (Jitsi, Express, SQLite) made this project possible.
