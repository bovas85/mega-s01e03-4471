Reports covered: **374** of the 412 in #4471.

The shared parser reads every date month first. Tenants whose locale writes the day first get flipped dates (7 April shows as 4 July).

- 11 tenants, 2026-04-01 to 2026-10-04.
- Channels: app, email and form (form only for tenants not on booking-v3).
- Intake tagged 23 of the parser-cause reports as `hint`, so its tag is not reliable.
- This is the problem the queued fix in #4471 covers.

Counts come from `uniqueById` (427 export rows, 15 duplicate ids, 412 unique) and `causeOf` in `src/lib/kb/causes.ts`, minus the 5 reports in issue "one-day move".

Page: src/routes/kb/incidents/4471-three-problems/+page.svx
