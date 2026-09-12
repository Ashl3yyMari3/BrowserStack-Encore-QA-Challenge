# Ticket 2 — SAVE10 Discount-Rule Automation

**Required ticket**

## Objective
Automate a booking that proves whether SAVE10 follows the PRD rule: apply 10% off **Standard seats only**, while VIP seats remain full price.

## Test design
- Event: Neon Skyline
- Standard seat C1: $65.00
- VIP seat A1: $120.00
- Expected Standard price after discount: $58.50
- Expected VIP price: $120.00
- Expected total: **$178.50**

## Confirmed result
The application discounted the VIP seat too:
- Actual VIP price: **$108.00**
- Actual total: **$166.50**

This is an application business-rule defect. The automated test intentionally fails until the discount calculation is corrected.

## Evidence
- [Public BrowserStack automation run](https://test-management.browserstack.com/projects/4123181/test-runs/73530955?public_token=5df2852aef156a72ee192efff76ba1a1d69d2f718bcc5cf14339234c23e52d46ac1fa75dbed136e5a3d787b5d22d9fa2bff705b833f26661e32df83c45838934&public_token_id=24436)
- [WebdriverIO/Appium test](../../automation/save10-discount.spec.js)
- [Original working-fork commit](https://github.com/Ashl3yyMari3/encore-test-suite/commit/57134c583ea67d2c4989658838f08504c4e87581)

## Final release label

- **Severity:** Critical
- **Call:** Block the release until it’s resolved
