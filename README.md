```bash
# Quick install (one-line, for lab setup)
# Run from project root: creates docker-based MailHog test environment
bash ./scripts/setup-mailhog.sh
```

---

# Phishing Awareness Lab — Quick Visual README

**Tagline:** Responsible phishing-simulation resources & isolated training lab

> This visual README is designed to be exported as a single high-quality Canva image (recommended size: 1600×900 px). It documents **installation**, **usage**, **safety & legal rules**, and **how to run the lab**. Use the design guide below to make it visually outstanding.

---

## 1) One-line Quick Start (Installation)

1. Clone repository:

```bash
git clone https://github.com/<your-org>/phishing-awareness-lab.git
cd phishing-awareness-lab
```

2. Start the test mail environment (Docker + MailHog):

```bash
bash ./scripts/setup-mailhog.sh
```

3. Verify UI: open `http://localhost:8025` to preview test messages.

---

## 2) Detailed Installation

**Requirements**

* Git
* Docker & Docker Compose
* Bash (Linux / WSL / macOS)

**Steps**

1. Clone the repo (see above).
2. Make script executable (if needed):

```bash
chmod +x ./scripts/setup-mailhog.sh
```

3. Run the script:

```bash
./scripts/setup-mailhog.sh
```

4. The script will pull `mailhog/mailhog` and expose ports `8025` (web UI) and `1025` (SMTP).
5. To stop and remove the container:

```bash
docker compose down --volumes
# or if you used `docker run`, find container id and `docker rm -f <id>`
```

---

## 3) Usage — Safe Training Workflow

1. **Prepare a safe test email** using `TEMPLATES/training-email-sample.txt`. Do **not** include external links or real recipient addresses outside the lab.
2. **Send test message** to MailHog SMTP (port 1025) — applications or scripts must point SMTP to `localhost:1025`.
3. **Check delivery & content** via MailHog UI at `http://localhost:8025`.
4. **Collect metrics**: track which participants opened or clicked in a controlled setting (use internal logging only).
5. **Report & debrief**: use `TEMPLATES/reporting-form.md` to collect feedback and lessons learned.

---

## 4) Scripts included (quick reference)

* `scripts/setup-mailhog.sh` — pulls and runs MailHog in docker (ports 8025, 1025).
* `scripts/teardown.sh` — stops and removes containers and volumes.
* `TEMPLATES/` — training email and reporting form templates.

---

## 5) Safety & Legal Checklist (MUST READ)

* ✅ Obtain **written authorization** from system owners before any simulation.
* ✅ Notify HR and Legal; define allowed scope, participants, timing.
* ✅ Never send to public or external recipients.
* ✅ Use dummy or test accounts only; avoid real PII.
* ✅ Provide an immediate take-down / stop procedure.

If any of the above cannot be met — do not run the test.

---

## 6) Best Practices for a Professional Campaign

* Use clear internal messaging explaining the learning objective.
* Keep simulations short, limited in scope, and non-invasive.
* Provide training resources and follow-up workshops after the test.
* Maintain an incident log and anonymize participant data.

---

## 7) Troubleshooting

* If MailHog web UI is not reachable: ensure Docker is running and ports are not blocked.
* Check logs:

```bash
docker logs <container-id>
```

* Common fixes: restart Docker engine; free ports `8025`/`1025` if in use.

---

## 8) Contribution & Code of Conduct

Contributions are welcome but must align with the repository's non-offensive, defensive purpose. See `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` for rules.

---

## 9) Export & Canva Design Guide (how to make it visually exceptional)

**Canva canvas size:** 1600 × 900 px (landscape)

**Layout (three-column / tile-friendly):**

* Header (full-width): Project name, tagline, logo left, one-line code block (copyable) on the right.
* Main body (three tiles): Installation (tile 1), Usage (tile 2), Safety & Legal (tile 3).
* Footer (full-width): Quick scripts list, contact/maintainers, license badge.

**Typography:**

* Header title: Inter or Montserrat (bold, 36–48pt)
* Section headings: 18–22pt
* Body text: 12–14pt
* Code block: monospace font (e.g., Inconsolata) in a rounded rectangle with subtle shadow

**Color palette suggestion:**

* Primary: #0B5FFF (deep blue)
* Accent: #06B6D4 (teal)
* Neutral background: #F8FAFC (very light gray)
* Danger (warnings): #F97316 (orange)

**Visual elements:**

* Add 2–3 icons (installation, shield/legal, mail) to the tiles.
* Show a small MailHog screenshot (assets/mailhog-sample.png) in the Usage tile.
* Add badges: License (MIT), Docs status (docs build passing), Repo topic tags.

**Accessibility:**

* Ensure 4.5:1 contrast for text on background.
* Use large click targets and readable font sizes.

**Export recommendations:**

* Export as PNG at 2x resolution for crispness (3200×1800 px). Provide an SVG if using vector elements.

---

## 10) Contact & Maintainers

* Maintainer: Security Training Team — [[security@example.com](mailto:security@example.com)]
* Repo: `github.com/<your-org>/phishing-awareness-lab`

---

## 11) License

This document and templates are distributed under the MIT license. See `LICENSE` for full text.

---

*If you want, I can now:*

1. Generate a Canva-ready PNG (with layout) — or provide the file contents to paste into Canva.
2. Produce the README as both English and Arabic variants.
3. Create the `scripts/setup-mailhog.sh` and other small helper scripts here.

Which option would you like next?
# Phishing-Awareness-Lab
