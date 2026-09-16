# Ticket 5 — Seat-Selection Accessibility

**Optional Ticket**

## Objective

Scan the seat-selection experience using BrowserStack Accessibility, identify the most severe accessibility issue detected, document the applicable WCAG requirements, and record the recommended correction.

## Accessibility Scan

-Evidence in file

## Scan Summary

The BrowserStack Accessibility scan identified **59 total accessibility issues** across **6 rules**.

| Severity | Issues |
|---|---:|
| Critical | 1 |
| Serious | 37 |
| Moderate | 9 |
| Minor | 12 |

The most severe finding was classified as **Critical**.

## Most Severe Finding

### Interactive Element Accessibility Label

BrowserStack flagged an event-card button because its accessibility label did not fully represent the meaningful information presented to the user.

### Detected Accessibility Label

`Crowd Work Only, Comedy, from $24, Button`

The event card also visually presents additional information such as the venue, date, and event time.

BrowserStack recommended using a more complete and descriptive accessibility label.

## Recommended Accessibility Label

`Crowd Work Only at Laugh Lounge, Thursday, October 8, 2026, 8:00 PM, tickets starting from 24 dollars`

This provides screen-reader users with clearer context about the event without requiring them to visually inspect the card.

## WCAG Requirements

BrowserStack associated the finding with the following WCAG 2.1 criteria:

- **WCAG 2.1 — 1.3.1: Info and Relationships — Level A**
- **WCAG 2.1 — 2.4.6: Headings and Labels — Level AA**
- **WCAG 2.1 — 4.1.2: Name, Role, Value — Level A**

## Recommended Fix

Update the interactive event-card accessibility label so that it communicates the important information displayed on the card, including:

- Event name
- Venue
- Date
- Time
- Starting ticket price

A descriptive label such as:

`Crowd Work Only at Laugh Lounge, Thursday, October 8, 2026, 8:00 PM, tickets starting from 24 dollars`

would give assistive-technology users more complete context about the event.

## Severity and Release Decision

| Field | Result |
|---|---|
| **Severity** | Critical |
| **Release Call** | Fix it |

## Screenshot Evidence

The BrowserStack Accessibility screenshot shows the flagged interactive element, detected accessibility label, Critical severity, associated WCAG criteria, and BrowserStack's recommended replacement label.

```md
![Ticket 5 Accessibility Finding](./evidence/ticket-5-accessibility-finding.png)
