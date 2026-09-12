# Ticket 6 — Exploratory 10-Seat Payment Journey

**Optional ticket**

## Objective
Use Test Companion to explore a complete booking with a large seat selection and continue through payment, recording what happens at every stage.

## Environment
- Galaxy S22
- Android 13
- Event: Neon Skyline
- Venue: Riverside Arena
- Event date: October 10, 2026 at 7:30 PM

## Test data
- VIP seats A1–A5: $120 each
- Standard seats C1–C5: $65 each
- Total selected: 10 seats
- Expected/displayed total: **$925.00**

## Confirmed result
After **Confirm Payment**, the payment-processing indicator continued spinning indefinitely. The application remained on the Payment screen and never completed the booking.

## Evidence
- [Full activity-feed evidence](./evidence/neon-skyline-activity-feed.png)
- [Payment-spinner session report](./evidence/payment-spinner-session-report.png)
- [Condensed evidence dashboard](./evidence/payment-spinner-evidence-dashboard.png)

The evidence contains the mobile steps, maximized activity feed, page-source confirmation for all 10 selected seats, and the indefinite payment-spinner state.
