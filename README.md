<div align="center">

Hermes Dashboard
Open-source marketing operations control center for AI agent teams.
Run CRM, outreach, content, analytics, and automation workflows from one dashboard, powered by OpenClaw + SQLite.

[ [ [ [ [

</div>

Alpha software — Hermes Dashboard is actively developed. Expect API, schema, and configuration changes between releases.

Why Hermes Dashboard?
Hermes is designed for operator-led AI marketing systems that need execution visibility and centralized control.

Unified marketing platform — CRM, outreach, content ops, analytics, experiments, and automations in one place.

OpenClaw-native — Dynamic agent and squad discovery, cron templates, and workspace/comms surfaces.

Local-first — Built on Next.js + SQLite so it runs locally without required external infra.

Secure-by-default — Session auth, API keys, host lock, and writeback controls are conservative by default.

Production-ready features — Deploy status, audit trails, role-based access, and covered auth/API flows.

Screenshots
Overview
CRM
Quick Start
Requires pnpm (install with npm install -g pnpm or corepack enable).

bash
git clone https://github.com/your-org/hermes-dashboard.git
cd hermes-dashboard
pnpm install
pnpm env:bootstrap
pnpm dev
Open http://localhost:3000.
On first run, an initial admin user is seeded from AUTH_USER / AUTH_PASS if the users table is empty.

Project Status
What works
CRM: leads, pipeline funnel, source tracking, engagement APIs.

Outreach: sequencing, pause/audit endpoints, suppression workflows.

Content ops: calendar, items, performance APIs.

Analytics/KPIs: views with optional connectors (Plausible, GA4, social).

OpenClaw discovery: dynamic agents and squads.

Cron templates: OpenClaw-compatible schedules (cron, every, at).

Deploy preflight: OpenClaw config validation endpoint.

Auth: session + API key auth with role-based access.

Known limitations
Alpha stage: expect occasional schema and UI changes.

Some integrations require external provider setup and credentials.

Security considerations
Change seeded credentials (AUTH_USER, AUTH_PASS, API_KEY) before exposing to networks.

Keep host lock enabled unless broader access is required (HERMES_HOST_LOCK=local by default).

Keep writeback flags disabled unless needed:

HERMES_ALLOW_POLICY_WRITE=false

HERMES_ALLOW_CRON_WRITE=false

HERMES_ALLOW_WORKSPACE_WRITE=false

Never commit real credentials or personal data.

Architecture
Layer	Technology
Framework	Next.js 16 (App Router)
UI	React 19 + TypeScript
Data	SQLite (local state in ./state)
Agent Runtime	OpenClaw CLI + filesystem integration
Auth	Session cookie + API key + optional Google OAuth
Configuration
See .env.example for the full list.

Required
AUTH_USER

AUTH_PASS (minimum 10 chars)

API_KEY

AUTH_COOKIE_SECURE (false for local HTTP dev, true for HTTPS)

OpenClaw / multi-instance
HERMES_OPENCLAW_HOME

HERMES_DEFAULT_INSTANCE

HERMES_OPENCLAW_INSTANCES (optional JSON array)

Optional 1Password runtime overlay
HERMES_1PASSWORD_MODE=off|auto|required (auto default)

HERMES_OP_ENV_FILE=/etc/hermes-dashboard/hermes-dashboard.op.env

Example mapping: ops/1password/hermes-dashboard.op.env.example

Host access lock
HERMES_HOST_LOCK=local (default)

HERMES_HOST_LOCK=off

HERMES_HOST_LOCK=host1,host2

Development
Common commands:

bash
pnpm dev
pnpm build
pnpm typecheck
pnpm lint
pnpm test
pnpm test:e2e
Template export and hygiene
Before publishing or sharing a template:

bash
./scripts/template-audit.sh
./scripts/template-export.sh [output_dir]
Export excludes sensitive/runtime artifacts such as .env*, database files, .next, and node_modules.

Open source
License: MIT

Security: SECURITY.md

Contributing: CONTRIBUTING.md

Code of Conduct: CODE_OF_CONDUCT.md

Third-party notices: THIRD_PARTY_NOTICES.md

Contributing
Contributions are welcome — please read CONTRIBUTING.md before opening PRs.

Support the project
If Hermes helps you, consider supporting development.

[

Solana donations:
BYLu8XD8hGDUtdRBWpGWu5HKoiPrWqCxYFSh4oxXuvPg

<div align="center">

Need agent infrastructure, trading systems, or Solana apps built for your team?
Builderz ships production AI systems — 32+ products across 15 countries.
Get in touch | @nyk_builderz

</div>

License
[
To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work.

<p align="center">
<a href="https://star-history.com/#your-org/hermes-dashboard&Date">
<img src="https://api.star-history.com/svg?repos=your-org/hermes-dashboard&type=Date" alt="Star History" width="400">
</a>
</p>

