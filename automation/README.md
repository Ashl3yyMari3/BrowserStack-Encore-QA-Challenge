# Automation Evidence

This folder contains the JavaScript automation created or corrected during the Encore challenge.

## Included tests

- `save10-discount.spec.js` — Ticket 2 business-rule test proving SAVE10 must discount Standard seats only.
- `event-list-locator.spec.js` — Ticket 7 correction using a stable event resource ID after the list reorders.

## Run locally

1. Install Node.js 18 or later.
2. Run `npm install` inside this folder.
3. Supply BrowserStack credentials, uploaded app ID, device name, and Android platform version through a secure local configuration.
4. Run `npm test`.

The committed `wdio.conf.js` intentionally contains placeholders. Never commit a BrowserStack username or access key.
