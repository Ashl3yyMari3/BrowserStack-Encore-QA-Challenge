# Ticket 3 — Cross-Device Event-Date Validation

**Required Ticket**

## Objective

Run `EventDateDisplayTest` across multiple Android devices to compare how the event date and time are displayed.

The required device coverage included:

- Android 11 phone
- Android 14+ phone
- Android tablet
- Phone from another manufacturer

## Devices Tested

| Device | Android Version | Result |
|---|---:|---|
| Samsung Galaxy M32 | Android 11 | Passed |
| Samsung Galaxy S24 | Android 14 | Passed |
| Samsung Galaxy Tab S8 | Android 12 | Passed |
| Google Pixel 6 | Android 12 | Passed |

## Finding

The automated test passed successfully on all four devices, but a device-specific time-formatting difference was observed.

The **Samsung Galaxy S24 running Android 14** displayed the event time as:

`7:30 PM`

The other tested devices displayed the same event time as:

`19:30`

This creates inconsistent event-time formatting across supported Android devices.

## Expected Result

The same event date and time should be displayed using a consistent format across supported devices.

## Actual Result

- Samsung Galaxy M32 — `19:30`
- Samsung Galaxy S24 — `7:30 PM`
- Samsung Galaxy Tab S8 — `19:30`
- Google Pixel 6 — `19:30`

The event information itself remained correct, but the presentation format differed on the Galaxy S24.

## Severity and Release Decision

| Field | Result |
|---|---|
| **Severity** | Minor |
| **Release Call** | Fix it |

## BrowserStack Public Sessions

Add the public BrowserStack session links for each device below:

- **Samsung Galaxy M32 — Android 11:**  
  [`Public session link`](https://automation.browserstack.com/projects/Encore+Hackathon/builds/event-date-display+cross-device/1?tab=tests&testListView=spec&details=4215917954&public_token=733f008a4e9962edc71af3f79d88502d273f91ca743f44e4f4f04de1ed640994)

- **Samsung Galaxy S24 — Android 14:**  
  [`Public session link`](https://automation.browserstack.com/projects/Encore+Hackathon/builds/event-date-display+cross-device/2?tab=tests&testListView=spec&details=4215924718&public_token=733f008a4e9962edc71af3f79d88502d273f91ca743f44e4f4f04de1ed640994)

- **Samsung Galaxy Tab S8 — Android 12:**  
  [`Public session link`](https://automation.browserstack.com/projects/Encore+Hackathon/builds/event-date-display+cross-device/3?tab=tests&testListView=spec&details=4215927451&public_token=733f008a4e9962edc71af3f79d88502d273f91ca743f44e4f4f04de1ed640994)

- **Google Pixel 6 — Android 12:**  
  [`Public session link`](https://automation.browserstack.com/projects/Encore+Hackathon/builds/event-date-display+cross-device/4?tab=tests&testListView=spec&details=4215933368&public_token=733f008a4e9962edc71af3f79d88502d273f91ca743f44e4f4f04de1ed640994)

## Screenshot Evidence

The comparison screenshot shows that the Galaxy S24 displays the event time in **12-hour format** while the other tested devices display it in **24-hour format**.

```md
<img width="1672" height="941" alt="side by side comparison" src="https://github.com/user-attachments/assets/f6c7d286-294a-433e-bfd4-6ca628e1161c" />
