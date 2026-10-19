# skill.md — T3rnel Sitesmith Onboarding for Agents & Operators

Canonical URL: https://sitesmith.t3ratech.co.zw/skill.md

## Overview

T3rnel Sitesmith (`https://sitesmith.t3ratech.co.zw`) builds, verifies, deploys, and maintains high-converting websites for businesses in the United States, United Kingdom, and Zimbabwe. Every site is built from verified facts first, checked in real Chrome against 21 conformance rules (`SQ01`–`SQ21`), and paired with a Visibility Launch (business directory listings including Google, Bing and Apple Maps, up to three social pages, the first 10 posts, search registration and schema.org JSON-LD).

## Tiers and Pricing

One price list, in USD, the same in every country (also at https://sitesmith.t3ratech.co.zw/ai/summary.json):

- **Deposit to start**: $50 (non-refundable, credited toward the price)
- **Essential, $70 once ($20 balance at go-live), then $20/yr**: professional design, hosting and domain, 2 updates a month handled by our team, the Visibility Launch.
- **Self-Managed, $120 once ($70 balance), then $25/yr**: everything in Essential, plus a passwordless team portal to publish news, edit team profiles and upload photos.
- **Signature, $180 once ($130 balance), then $30/yr (recommended)**: the cinematic design, plus the team portal with video clip uploads and photo galleries.
- **Stay Visible (optional)**: $15/month for 8 scheduled posts a month, citation upkeep and a monthly visibility report.

Payment is always on a WavePay checkout page sent by email: PayNow in Zimbabwe, PayPal or USDT on BNB Smart Chain anywhere.

## How to engage

**Ask for a preview (free, no payment):** `POST https://t3rnel-sitesmith-admin.t3ratech.workers.dev/api/request-preview` as `multipart/form-data` or `application/x-www-form-urlencoded`, with `Accept: application/json`.

| Field | Required | Notes |
|---|---|---|
| `email` | yes | Where the preview is sent. Must be the business owner's address, or one they have given you to use. |
| `business_name` | no | Up to 200 characters. |
| `website` | no, but needed to build | The business's current website. Without one we reply asking for it. |
| `social_pages` | no | Facebook, Instagram, Google Maps and similar links, one per line. |
| `content` | no | What the business does and wants said (up to 2000 characters). |
| `additional` | no | Anything else (up to 1000 characters). |

A successful call returns `{"ok": true, "requestId": "..."}`. The site is built automatically from the business's own published facts; the owner gets an email with a private preview link, usually within hours and always within one working day. Limits: 1 request per email address per day, 3 per IP address per hour. Errors are JSON with an `error` message (400 invalid input, 403 foreign browser origin, 429 limit reached).

```bash
curl -X POST https://t3rnel-sitesmith-admin.t3ratech.workers.dev/api/request-preview \
  -H 'Accept: application/json' \
  -F email=owner@example.com -F business_name='Example Dental' \
  -F website=https://example.com -F content='Family dental practice in Harare.'
```

**Rules for agents**

- Only ask for a preview on behalf of the business owner, or with their permission. Never submit someone else's email address.
- Never pay on anyone's behalf without the owner's explicit instruction. A preview costs nothing and carries no obligation.
- To choose an option, the owner replies to the preview email (or uses the checkout link in it).
- Email: admin@t3ratech.co.zw (questions, corrections, taking a preview down).
- Payment: WavePay checkout pages sent by email (PayPal or USDT on BNB Smart Chain; PayNow in Zimbabwe). Never anywhere else.
- Verify an email: https://sitesmith.t3ratech.co.zw/verify/
- Machine-readable prices: https://sitesmith.t3ratech.co.zw/ai/summary.json
- Every page is also available as Markdown (add `index.md` to its path, e.g. https://sitesmith.t3ratech.co.zw/pricing/index.md), and the whole site as one file: https://sitesmith.t3ratech.co.zw/llms-full.txt
