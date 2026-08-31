# Nicolás Andrés Cano Leal

**Backend Python & automation, heading to SRE.**
I replace manual operational processes with tested, observable, automated systems — and I run them in production.

📍 Rancagua, Chile · UTC-4 · open to remote work (EN/ES)
🌐 [nicolasandrescl.pythonanywhere.com](https://nicolasandrescl.pythonanywhere.com) · 💼 [LinkedIn](https://www.linkedin.com/in/nicolas-andres-cano-leal) · 📧 nicolas.cano.leal@gmail.com

---

## What I do

I'm a **Live Performance Agent at PedidosYa Chile** (LiveOps / BizOps) and the **sole developer on my operations team**. That combination is the point: I sit inside the operation, so I know which 40 minutes of manual work are worth killing before I write a line of code.

Formal training in Ingeniería en Informática (IP Santo Tomás) and 2,500+ hours of self-directed study since February 2025, structured with the Ultralearning method. Previous career as a nursing technician (TENS) — which is where the habit of working under pressure without dropping the checklist comes from.

---

## Selected work

### 🤖 LiveOps Engine "Jaime" — production, company-owned (private repo)

The automation platform my team runs on every day. Inherited from a colleague in April 2026 and evolved solo since; ~253 of the repo's 573 commits are mine, covering every version from 4.0 to 6.3 (11 releases in ~4 months).

- **~41,000 lines across 173 modules**, **723 tests**, CI on GitHub Actions
- **10 engines running in parallel** over 8 isolated browser profiles, each on its own schedule (dispatch monitoring, reporting, alerting, 3-day forecast, end-of-day closing, operator presence)
- Integrations: Selenium 4 / Playwright over the internal dispatch platform, Google Sheets (8 sheets), Slack, **BigQuery**, Grafana PDF parsing with pdfplumber
- **10,000 orders reassigned in July 2026 alone**

Engineering highlights: zero-downtime UI migration from CustomTkinter to NiceGUI using a strangler-fig pattern; thread-safe reassignment cooldown system; a real fix for a `RecursionError` caused by three wrappers reassigning `sys.stdout` without a lock (routed streams via `threading.local` + reentrancy guard); cross-process log rotation with a PID-validated single-instance lock; a dedicated "clean house" release that removed ~12k lines of dead UI and cut `config.py` from 923 to 199 lines.

Measured results: bucket report **20–25 min → under 5 min**; Google Sheets read latency **~16 min → under 1 min**; reassignment bottleneck **~37 min → ~10 min** (by proving the cost was the platform's cooldown, not my code).

Presented to ~100 people at the Log & Ops Summit, July 2026.

---

### 🧱 [All in Django](https://github.com/NicolasAndresCL/All_in_Django) — public

Django 6 + DRF rebuild of a Streamlit mega-project that had consolidated 7 earlier ones. Study calendar, personal and team shift management, task log, notes and a scraping module — one HTTP contract, UI fully decoupled from the ORM.

- Python 3.14, Django 6, DRF, pydantic-settings, Postgres 16 (psycopg v3), gunicorn + WhiteNoise
- **122 tests, ~83% coverage**; TokenAuth + throttling everywhere, `check --deploy` clean
- Full IaC: multi-stage non-root Docker + Compose with healthchecks, GitHub Actions, **Terraform (EC2 + RDS)**, Helm/K8s manifests, and CD through a declarative Jenkinsfile deploying GHCR images

---

### 🐧 [ultimate-linux-lab](https://github.com/NicolasAndresCL/ultimate-linux-lab) — public

A disposable Linux lab in Docker: Ubuntu 24.04 with **real systemd as PID 1**, a GNOME desktop reachable from the browser (TigerVNC → noVNC, bound to loopback only), dual persistence, non-root user.

- Split into two stages: `base` (539 MB, 2–3 min) and `desktop` (2.67 GB)
- CI with hadolint, shellcheck, compose validation, a smoke test against the real container, **Trivy with SARIF** to the Security tab, and publishing to GHCR — plus a hardening check that verifies ports stay on loopback and the password stays parameterizable
- Dependabot, issue/PR templates, Conventional Commits, MIT

Built after a hand-configured VM corrupted itself. The lesson it encodes: infrastructure you can't rebuild from a file isn't infrastructure.

---

### 🔍 Incident dossier collector — private (handles real personal data)

Django/DRF + NiceGUI service over BigQuery that assembles investigation dossiers from six sources, replacing ~40 minutes of manual collection across four tabs.

- Pure resolver core with IO at the edges; **185 tests, none touching the network** (BigQuery client injected as a double, fixtures captured from real responses)
- No models, no local DB — the dossier is read fresh each time so a second source of truth never appears
- Deliberate design constraint: **the system never concludes anything.** No verdict, score or recommendation fields, enforced by a test that fails if anyone adds them
- Ships two documented gaps instead of papering over them, and reports upstream failures explicitly rather than returning an empty 200

---

## Stack

**Languages** Python (primary), SQL, Bash, some Java and JavaScript
**Backend** Django · DRF · FastAPI · Flask · NiceGUI · Pydantic · OpenAPI
**Data** BigQuery · PostgreSQL · MySQL · pandas · NumPy · PySpark · Power BI
**Automation** Selenium · Playwright · gspread · Slack SDK · n8n · VBA→Python migrations
**Infra & CI/CD** Docker · Compose · GitHub Actions · Jenkins · Terraform · Kubernetes/Helm · GHCR · Trivy · Linux · systemd
**Practice** pytest · Conventional Commits · CI wired from day one · ruff

---

## Where I'm heading

Target role: **Site Reliability Engineer**, international remote market. Path I'm walking deliberately: Backend → DevOps → SRE → Software Architect.

Certifications in progress, chosen against my actual gaps: **Terraform Associate**, **Google Cloud Professional Cloud DevOps Engineer**, **CKA**, **Prometheus Certified Associate**.

I know my current bottleneck: I'm a sole developer, so nobody reviews my architecture but me. I'm looking for a team where that stops being true.

---

> *"El buen software no solo se escribe, se entiende y se evoluciona."*
> *"Good software isn't just written — it's understood and evolved."*
