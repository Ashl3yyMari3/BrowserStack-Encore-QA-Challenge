# Ticket 8 — Shared-Venue Seat Availability

**Optional ticket**

## Objective
Book a seat at one event, inspect other events hosted at the same venue, and determine whether seat availability incorrectly carries between separate events.

## Confirmed result
Both checked events were hosted at **Laugh Lounge**. Seat C1 appeared with:

`Seat C1, standard, booked, $38`

even though that seat had never been booked for the second event. Seat inventory was incorrectly shared or leaked between separate events at the same venue.

## Evidence
- [Test Companion evidence dashboard](./evidence/shared-venue-seat-bug.png)

The dashboard confirms the unexpected booked state and preserves the Test Companion finding.

## Final release label

- **Severity:** Critical
- **Call:** Block the release until it’s resolved
