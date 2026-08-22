# Email Signup → Storage + Welcome Email

Plan for wiring the "Sign up for updates" form once Google Workspace is active.

## Storage: Google Sheets
- Google Cloud project with Sheets API enabled
- Service account (JSON key) shared as editor on the target Sheet
- Form submits to a backend, which appends a row via the Sheets API

## Welcome email — two options
1. **Google Apps Script** (recommended to start): script bound to the Sheet, triggers on submission, appends row + sends email via MailApp/GmailApp. No separate hosting.
2. **Transactional email service** (Postmark, Resend, SendGrid): called from a backend function. Better deliverability/tracking at scale; needs a domain-verified sender.

## What the site needs
- A backend endpoint to POST to (Apps Script web app URL, or a serverless function — Cloudflare Worker / Vercel function). The static page can't call Sheets/Gmail directly without exposing credentials.
- Spam protection on the public form (honeypot field or basic rate limiting).
- A verified sending domain (e.g. hello@unpairedsocks.com) rather than a default Gmail address — also helps credibility with manufacturers.

## Simplest path
Apps Script web app + Sheet. Once it exists, send Claude the web app URL to wire up the form submit.
