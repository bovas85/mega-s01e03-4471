Reports covered: **33** of the 412 in #4471.

Tenants on booking-v3 (`alder.physio`, `copper.studio`, `pale.harbour`) have day-first locales (de-DE, es-ES, pt-PT), but their form prints `MM/DD/YYYY` under the date field. People type what the hint says, month first, and the form reads it their way.

- Only form-channel reports from those three tenants. 2026-04-17 to 2026-09-22.
- Intake tagged 15 of these 33 as `parser`; only 18 as `hint`.
- Fixing the parser does not fix this. It needs a change to the booking-v3 hint or its reading of the field.

Counts come from `causeOf` in `src/lib/kb/causes.ts`.

Page: src/routes/kb/incidents/4471-three-problems/+page.svx
