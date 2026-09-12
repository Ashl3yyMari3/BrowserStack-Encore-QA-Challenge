# BrowserStack Encore QA Challenge — Tickets 1–9

## Ashley Cichy | QA Engineer & Computer Science Student

This repository documents my individual release-readiness assessment of **Encore**, an Android event-ticket booking application, using BrowserStack Test Companion, App Live, App Automate, Test Management, Accessibility, and Test Reporting & Analytics.

The challenge required Tickets 1–4 and offered Tickets 5–9 as optional advanced work. I worked through all nine tickets, combining exploratory testing, AI-assisted test generation, WebdriverIO/Appium automation, cross-device validation, accessibility analysis, root-cause analysis, and release-risk decisions.

## Technology

- JavaScript / Node.js
- WebdriverIO + Mocha
- Appium
- BrowserStack Test Companion
- BrowserStack App Live and App Automate
- BrowserStack Test Management
- BrowserStack Accessibility
- Android real-device testing

## Ticket Index

| Ticket | Focus | Required? | Severity | Release call | Evidence status |
| --- | --- | --- | --- | --- | --- |
| [01](./tickets/ticket-01/README.md) | AI-assisted test design and PRD coverage | Yes | Critical | Block release | 136-case CSV published |
| [02](./tickets/ticket-02/README.md) | SAVE10 business-rule automation | Yes | Critical | Block release | Code and public run published |
| [03](./tickets/ticket-03/README.md) | Cross-device event-date validation | Yes | Minor | Fix it | Session evidence being consolidated |
| [04](./tickets/ticket-04/README.md) | VIP payment failure RCA | Yes | Blocker | Block release | RCA evidence being consolidated |
| [05](./tickets/ticket-05/README.md) | Seat-selection accessibility | No | Critical | Fix it | Scan evidence being consolidated |
| [06](./tickets/ticket-06/README.md) | Exploratory 10-seat payment journey | No | Critical | Block release | Bug and activity-feed evidence published |
| [07](./tickets/ticket-07/README.md) | Event-list locator RCA and fix | No | Major | Fix it | Corrected code published |
| [08](./tickets/ticket-08/README.md) | Shared-venue seat availability | No | Critical | Block release | Bug evidence published |
| [09](./tickets/ticket-09/README.md) | Tablet vs phone seats-remaining behavior | No | Critical | Block release | Session evidence being consolidated |

## Confirmed Findings

- **Ticket 2:** SAVE10 incorrectly discounted a VIP seat. The automated test expected Standard-only discounting and documented the incorrect $166.50 total instead of $178.50.
- **Ticket 6:** A 10-seat $925 booking reached payment, but the payment-processing spinner remained active indefinitely.
- **Ticket 8:** Seat C1 appeared booked for another event at the same venue even though it had not been booked for that event.
- **Ticket 7:** The failing event-list automation used an unstable index/position assumption. The corrected test uses the event's stable semantic resource ID after the list reorders.

## Source and Attribution

The original Encore APK, PRD, and starter scripts were supplied through the BrowserStack challenge repository. The test analysis, Ticket 2 automation, Ticket 7 correction, evidence organization, findings, and release-readiness documentation in this repository represent my individual challenge work.

- [Working fork and starter suite](https://github.com/Ashl3yyMari3/encore-test-suite)
- [Original shared repository](https://github.com/pujagani/encore-test-suite)

> Security note: BrowserStack usernames, access keys, application IDs, and other credentials are intentionally excluded.
