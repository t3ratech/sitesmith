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
| LLM index | `https://sitesmith.t3ratech.co.zw/llms.txt` | Structured links for answer engines |

## Verification & Anti-Scam Policy

- Every legitimate Sitesmith outreach email is sent from `admin@t3ratech.co.zw` (authenticated via SendGrid DKIM/SPF and routed inbound via ImprovMX to `teratech@agentmail.to`).
- Preview sites are hosted with `X-Robots-Tag: noindex, nofollow` so they never compete with the business's existing site in search engines.
- All payments go exclusively through **T3rnel WavePay** (`PayNow`, `PayPal`, or `USDT` on BNB Smart Chain). We never ask for passwords or bank credentials by email.
