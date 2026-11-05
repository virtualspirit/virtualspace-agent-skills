---
name: virtualspace-calendar
description: Find and review VirtualSpace calendar events, suggest meeting times from visible events, or create a requested event with a confirmed time zone and attendees.
---

# VirtualSpace Calendar

Confirm the date window and time zone. Use `calendar.events.search` and `calendar.events.get` to find relevant visible events. Compare start and end times in the requested time zone. Report an incomplete search if the relevant pages cannot be read.

Offer candidate slots as tentative based on visible events. If `calendar.availability.check` reports unsupported or cannot establish attendee coverage and recurring conflicts, say that availability is unverified. An empty event search alone does not establish free time.

Create an event only on explicit request with a clear title, start, end, time zone, and audience. Use `calendar.events.create`, then add the requested attendees using the supported attendee tools if needed. Check the event and attendee results. If attendee addition fails after event creation, report the existing event and retry only the missing step with its original operation ID.
