# Ticket 7 — Event-List Locator RCA and Correction

**Optional Ticket**

## Objective

Run the supplied `EventListLocatorTest` without modifying it, inspect BrowserStack Failure Analysis, determine whether the failure is an **App Bug** or **Automation Issue**, correct the automation when appropriate, and verify the fix with a passing rerun.

---

## Failure Observed

The original automation expected to reopen:

`Late Night Jazz`

but instead opened:

`City Derby Night`

The application had reordered the event list after **Late Night Jazz** became sold out.

Because the automation relied on the event's previous list position, the same screen location no longer pointed to the expected event after the list changed.

---

## Root Cause

The failure was caused by the **automation**, not the Encore application.

The original test relied on an unstable list index/on-screen position to reopen the previously selected event.

After **Late Night Jazz** sold out, the event list reordered. The automation then reused the original position, which now corresponded to **City Derby Night**.

### Classification

**Automation Issue**

---

## Resolution

The automation was updated to stop relying on the event's list position.

Instead, the corrected test locates the sold-out event using its stable semantic resource ID:

```text
event-card-soldout-evt-17
```

Using a stable resource ID allows the automation to locate the intended event even when the order of the event list changes.

The corrected test was rerun successfully on BrowserStack.

---

## Before vs After

### Original Approach

The test relied on the event's position within the list.

When the list reordered, the locator no longer identified the intended event.

### Corrected Approach

The test uses a stable semantic locator tied to the event itself:

```js
event-card-soldout-evt-17
```

This makes the automation resilient to list reordering.

---

## Evidence

### Failed BrowserStack Run

[View the original failed BrowserStack run](https://automation.browserstack.com/builds/85ej90aaqeudhuydyc82phjtegsczhtqecm6xdtt)

**Expected:** `Late Night Jazz`  
**Received:** `City Derby Night`

### Corrected Automation

[View the corrected WebdriverIO/Appium test](https://github.com/Ashl3yyMari3/BrowserStack-Encore-QA-Challenge/blob/main/automation/event-list-locator.spec.js)

### Working Fork Version

[View the corrected test in the working fork](https://github.com/Ashl3yyMari3/encore-test-suite/blob/main/nodejs/test/specs/event-list-locator.spec.js)

### Original Fix Commit

[View the original working-fork commit](https://github.com/Ashl3yyMari3/encore-test-suite/commit/00e7758a04b131cc907d5abb0eea0cfca1c9bbed)

### Passing BrowserStack Rerun

[View the passing BrowserStack rerun](https://automation.browserstack.com/builds/drxk2lzr4jwryxdahsib8zptnvdmyym0mgolslib)

---

## RCA Evidence

BrowserStack Failure Analysis confirmed that the failure originated from the automation logic rather than the application.

The failure showed:

- **Expected event:** `Late Night Jazz`
- **Actual event opened:** `City Derby Night`
- Event list reordered after the expected event sold out
- Original locator depended on the previous list position
- Stable semantic resource ID used in the corrected automation
- Corrected test passed after rerun

Add the RCA screenshot to the ticket evidence folder and reference it here:

```md
![Ticket 7 Root Cause Analysis](./evidence/ticket-7-rca.png)
```

---

## Classification

| Field | Result |
| --- | --- |
| **Classification** | Automation Issue |
| **Severity** | Major |
| **Release Call** | Fix it |

---

## Final Release Label

- **Severity:** Major
- **Classification:** Automation Issue
- **Call:** Fix it

---

## Outcome

Ticket 7 demonstrated the importance of using stable semantic locators rather than screen coordinates or list positions in mobile automation.

The failure was traced to the test implementation, corrected with a stable event-specific resource ID, and verified with a successful BrowserStack rerun.

## Evidence
- [Corrected WebdriverIO/Appium test](../../automation/event-list-locator.spec.js)
- [Original working-fork commit](https://github.com/Ashl3yyMari3/encore-test-suite/commit/00e7758a04b131cc907d5abb0eea0cfca1c9bbed)

