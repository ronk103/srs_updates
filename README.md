# Member Data Update Automation Suite


<!-- ... -->

### Overview

A Python automation suite that replaces manual, ticket-by-ticket updates
with a scrape → extract → review → batch-update → close pipeline.

It scrapes tickets via browser automation (no export feature exists),
extracts structured fields from unstructured notes, and applies
validated, auditable updates to both an internal Excel database and
external bank files — cutting a multi-hour manual process down to
minutes.

### Why I Built This

The existing process required manually opening each ticket, reading
through comments and notes, transcribing relevant fields (addresses,
phone numbers, banking details, dates of death, status changes) into a
working file, and separately re-entering that data into both the
internal database and a bank submission file — 2-3x a month, for 70-100+
tickets per cycle. Tickets then had to be closed or reassigned by hand
one at a time.

This process had no safety net: no changelog, no reliable way to answer
“what changed for member so-and-so, on what date, and to which fields,”
and no protection against an accidental overwrite silently propagating
into a payment or tax record. It was also entirely manual labor with no
reuse — every cycle started from zero.

I built this suite to remove the repetitive, error-prone parts of the
workflow while keeping a human in the loop exactly where judgment is
still needed: reviewing extracted data and handling edge cases, not
re-typing information that’s already sitting in a ticket.

### Key Benefits

- **~82% reduction in ticket processing time** — an estimated 12–14
  hours saved per month, based on ~70–100 tickets per cycle, 2
  cycles/month
- **Automated file preparation** — the two monthly submission files
  (main + off-cycle) are ~90% auto-generated; the remaining manual
  portion takes ~20 minutes, versus an estimated hour (or more) for
  someone doing it by hand
- **No accidental data loss** — blank fields are never treated as
  deletions; a separate explicit syntax is required to remove data
- **Full audit trail** — every update automatically generates a
  before/after changelog, closing the “what changed, for whom, and when”
  gap entirely
- **Automated ticket handling** — replaces opening and reading 70–100+
  tickets one by one with an effortless automated scrape that exports
  all tickets and comments into one Excel file. Automates closing and
  re-assigning the tickets once the update is complete.  
- **Built for scale and reuse** — the core modules, with minor tweaking,
  can be adapted to any workflow where data is tracked manually across
  tickets or spreadsheets.
