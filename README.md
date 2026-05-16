# Hey, I'm Benjamin 👋


I run production workloads on Linux, Docker, and AWS — coming from a SysAdmin background and now focused on infrastructure automation, container hardening, and observability. I learn by building small but real systems end-to-end: design, ship, audit, retro. The repos below are the receipts.

---

## What I work on

- **Linux + Docker** — VPS hardening (ufw-docker, systemd, fail2ban), multi-tenant container orchestration with Traefik + Let's Encrypt, container security (USER non-root, `cap_drop:ALL`, `read_only` rootfs, `no-new-privileges`)
- **AWS** — currently studying for **Solutions Architect Associate**; production work so far on Hostinger VPS as the proving ground for the patterns I'll port to AWS
- **CI / Automation** — image-build pipelines, scheduled jobs (launchd + cron), atomic deploy scripts, backup discipline (Postgres + memory rsync to iCloud)
- **Observability + Security** — structured JSON logs with secret-shape redaction, threat-class audits, policy-enforcement engines, SSRF defense, privilege-boundary sidecars
- **Python + TypeScript + Vue 3** — full-stack when needed, but my centre-of-gravity is the infrastructure layer
- **AI integrations** — MCP servers, custom Hermes-agent plugins, multi-LLM workflows (Claude + Codex) for review and adversarial-audit pipelines

---

## Selected projects

Each repo follows a 7-stage delivery workflow (Plan → Tests → Implement → Review → Security → Ship → Retro) with conformity-audit history. Architecture decisions (ADRs) and retros are committed alongside the code. Repos are private; happy to share access for interview review.

| Project | What it does | Stack |
|---|---|---|
| **agency-kernel** | Multi-project ops kernel: ADRs, skills, playbooks, shared Python substrate (`kb/lib/`). Includes a mechanical conformity-audit script that gates phase-closes. | Bash · Python · Markdown · launchd |
| **hermes-deployment** | First production deploy: Hermes Agent on a hardened Hostinger VPS. Telegram interface, OAuth, no inbound ports. | Docker · Telegram · OAuth · Ubuntu hardening |
| **phase-2b-hermes-autonomy** | Hermes plugin with policy-driven autonomy: action-log, secret redaction, cron governance. 49 unit-tests covering policy decision branches. | Python · YAML policy engine · pytest |
| **model-content-archiver** | Telegram bot pipeline behind a hardened multi-container stack (bot + FlareSolverr sidecar + Playwright sidecar). Privilege-boundary split keeps Chromium sandbox-escape away from bot secrets. | Docker Compose · Python 3.12 · Playwright · async httpx · Fernet vault |
| **job-agent** | Half-autonomous job-application assistant: multi-source scraping, Postgres-backed pipeline, Hermes plugin for Telegram review, CV-tailoring with truthful-only validator (catches LLM fabrication at validation time). | Python · PostgreSQL · Telegram · LLM integration · 856+ tests |
| **smart-hausverwaltung** | Vue 3 + FastAPI SaaS for German property managers. Cut-over from Proxmox VM to Hostinger VPS behind shared Traefik with Let's Encrypt + BasicAuth demo-gate. Multi-tenant Postgres co-residency with anchored-regex volume safety. | Vue 3 · FastAPI · PostgreSQL · Traefik · Docker |
| **hermes-source-of-truth** | Image-build pipeline for our Hermes runtime: private GitHub fork + kernel-tracked Dockerfile + reproducible VPS-side build. Stops the "container has secrets baked in via `docker commit`" anti-pattern documented in our retros. | Docker BuildKit · git fork-discipline · multi-stage builds |

---

## Operating principles I follow

- **ADRs for non-trivial decisions** — `kb/adr/NNNN-title.md` format with context / decision / alternatives / consequences
- **Tests first** — failing test before the fix, every time, including for regressions
- **Multi-round adversarial review** — different model families (Claude + Codex) find different blind-spots; security-critical code gets at least 2 rounds
- **Mechanical audits** — `scripts/kernel-audit.sh` blocks phase-close on phantom references, missing retros, or commit-message-vs-diff drift
- **Honest retros** — what was repeated, what we extracted, what surprised us; deferred items go to drift-watch with explicit triggers
- **Owner-runs-prod** — orchestration is automated; sudo / live tokens / external comms / spend are explicit human checkpoints

---

## Currently learning

- AWS Solutions Architect Associate (target cert)
- Terraform (will replace the bash-deploy-scripts that currently live in the repos)
- Kubernetes (after I'm comfortable with ECS/EKS basics)

---

## Open to

DevOps Engineer / Cloud Engineer / Platform Engineer roles in DACH (Nürnberg + ~100 km commute) or fully remote.

- 📧 [benjamindoelz@gmail.com](mailto:benjamindoelz@gmail.com)
- 🌍 Nürnberg, Germany
- 🇩🇪 Native German · 🇬🇧 Professional English

If you want a deeper look at any of the projects above, I'll happily grant repo access for an interview — just ask.
