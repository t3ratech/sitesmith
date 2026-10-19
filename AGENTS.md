# AGENTS.md — T3rnel Sitesmith

> What this service is, and the rules for interacting with it as an AI agent or automated client. Canonical machine onboarding lives at https://sitesmith.t3ratech.co.zw/skill.md.

## What this is

T3rnel Sitesmith is a build-first website, local SEO, and Answer Engine Optimization (AEO) service operated by **Teratech Solutions (Private) Limited** (`https://t3ratech.co.zw`). We audit a business's current web presence, build a working private preview (`noindex`) using only the business's own published facts, and launch the production site within 3 working days of deposit payment via WavePay.

## Interfaces

| Interface | URL | Purpose |
|---|---|---|
| Public site | `https://sitesmith.t3ratech.co.zw/` | Service overview, pricing, how it works, FAQ, authenticity verification |
| Corporate page | `https://t3ratech.co.zw/sitesmith` | Company-level Sitesmith overview on the main T3raTech domain |
| Client Admin & Multi-Tenant Router | `https://t3rnel-sitesmith-admin.t3ratech.workers.dev` | Magic-link client portal (`/login`, `/sites`) and R2-backed multi-tenant site router (`/p/:slug/`, `/live/:slug/`) |
| WavePay Checkout API | `https://t3rnel-wavepay-production.t3ratech.workers.dev/v2/checkouts` | Deposit, balance, and renewal checkouts (`productId: "t3rnel-sitesmith"`) |
| OpenAPI contract | `https://sitesmith.t3ratech.co.zw/openapi.json` | Machine-readable API specification |
| Agent card | `https://sitesmith.t3ratech.co.zw/.well-known/agent-card.json` | A2A discovery card |
| LLM index | `https://sitesmith.t3ratech.co.zw/llms.txt` | Structured links for answer engines (each page also has a Markdown copy at `<path>/index.md`) |
| Whole site as text | `https://sitesmith.t3ratech.co.zw/llms-full.txt` | Every page in one Markdown file |
| Preview request API | `POST https://t3rnel-sitesmith-admin.t3ratech.workers.dev/api/request-preview` | Ask for a free preview website for a business (see below) |

## Verification & Anti-Scam Policy

- Every legitimate Sitesmith outreach email is sent from `admin@t3ratech.co.zw` (authenticated via SendGrid DKIM/SPF and routed inbound via ImprovMX to `teratech@agentmail.to`).
- Preview sites are hosted with `X-Robots-Tag: noindex, nofollow` so they never compete with the business's existing site in search engines.
- All payments go exclusively through **T3rnel WavePay** (`PayNow`, `PayPal`, or `USDT` on BNB Smart Chain). We never ask for passwords or bank credentials by email.

## Requesting a preview (agents and scripts)

`POST https://t3rnel-sitesmith-admin.t3ratech.workers.dev/api/request-preview` with `Accept: application/json` and form fields `email` (required), `business_name`, `website`, `social_pages`, `content`, `additional`. It returns `{"ok": true, "requestId": "..."}`; the build is automatic and the preview link arrives by email, usually within hours and always within one working day. Full field list and an example are in https://sitesmith.t3ratech.co.zw/skill.md and https://sitesmith.t3ratech.co.zw/openapi.json.

- Submit only for the business owner, or with their permission, and only with an email address they own. One request per email address per day.
- A preview is free and carries no obligation. Do not pay for anyone without their explicit instruction.
- If the business has no website, put what you know in `content` and the Google Maps or social links in `social_pages`.
