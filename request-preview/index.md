# Request a preview

We study your business, build a better site from the facts you already publish, and show it to you privately. You decide after you have seen it.

## What we need from you

Fill in the form below. The more you tell us, the better your preview will be. All fields are optional except your email.

(The request form is on the web page. To ask for a preview from a program, see "Requesting a preview" below.)

**What happens next:**

- We review your request (usually within 1 working day)
- We study your existing web presence (your site, social pages, directories)

- We build a private preview of a better website for your business
- We email you a link to the preview (hidden from search engines)

- You decide: if you like it, choose an option and pay the deposit. If not, reply "no thanks" and we delete it.

*Requests are processed in the order received. Providing complete information helps us prioritize your request.*

## Requesting a preview

Using an AI assistant or a script? A preview can be requested without the form, for the business owner or with their permission. Send POST https://t3rnel-sitesmith-admin.t3ratech.workers.dev/api/request-preview with Accept: application/json and the fields email (required), business_name, website, social_pages, content and additional. It returns {"ok": true, "requestId": "..."} and the preview arrives by email. A preview is free and carries no obligation. One request per email address per day. The details are in [skill.md](https://sitesmith.t3ratech.co.zw/skill.md) and [openapi.json](https://sitesmith.t3ratech.co.zw/openapi.json).
