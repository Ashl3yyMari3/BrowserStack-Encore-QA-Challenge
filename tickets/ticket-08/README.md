# Ticket 8 — Shared-Venue Seat Availability

**Optional ticket**

## Objective
Book a seat at one event, inspect other events hosted at the same venue, and determine whether seat availability incorrectly carries between separate events.

## Confirmed result
Both checked events were hosted at **Laugh Lounge**. Seat C1 appeared with:

`Seat C1, standard, booked, $38`

even though that seat had never been booked for the second event. Seat inventory was incorrectly shared or leaked between separate events at the same venue.

## Evidence
The Test Companion evidence dashboard confirms the unexpected booked state. The activity-feed image will be added after final file verification.

## Final label
The final challenge severity and release call are being copied from the submitted ticket record before publication.
