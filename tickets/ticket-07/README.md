# Ticket 7 — Event-List Locator RCA and Correction

**Optional ticket**

## Objective
Run the supplied EventListLocatorTest unchanged, inspect Failure Analysis, decide whether the failure is an App Bug or Automation Issue, and correct/re-run it when appropriate.

## Root cause
The automation relied on a list index/on-screen position. After **Late Night Jazz** sold out, the event list reordered, so the original position no longer represented the same event.

## Resolution
The corrected automation locates the sold-out event through its stable semantic resource ID, `event-card-soldout-evt-17`, instead of relying on the original index.

## Evidence
- [Corrected WebdriverIO/Appium test](../../automation/event-list-locator.spec.js)
- [Original working-fork commit](https://github.com/Ashl3yyMari3/encore-test-suite/commit/00e7758a04b131cc907d5abb0eea0cfca1c9bbed)

## Classification
**Automation Issue**

The final challenge severity and release call are being copied from the submitted ticket record before publication.
