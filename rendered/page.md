# #4471 - three problems, not one

owner **Leelium** | status **living** | reviewed 2026-10-28

[#4471](/kb/incidents/4471) merged 412 reports as one issue. Read one by one, they are three different problems.

> Not one issue. Three problems need three tickets, each with its own count.

## The three problems

| problem | what | reports |
|---|---|---|
| `parser` | shared parser reads dates month first | 374 |
| `hint` | booking-v3 form hint says MM/DD/YYYY to day-first tenants | 33 |
| `one-day move` | date is exactly one day off, month not flipped | 5 |
| | merged into #4471 | **412** |

1. **parser** - the only problem the queued fix covers.
2. **hint** - `alder.physio`, `copper.studio`, `pale.harbour` (booking-v3). Parser fix does not fix this. Intake tagged 15 of the 33 as `parser`.
3. **one-day move** - R-41202, R-41209, R-41236, R-41344, R-41620. Looks like time zone or DST; five reports are too few to be sure.

## What the desk table says

| cause | reports | tagged as | tenants | seen |
|---|---|---|---|---|
| `parser` | 379 | parser 356, hint 23 | 11 | 2026-04-01 to 2026-10-04 |
| `hint` | 33 | hint 18, parser 15 | 3 | 2026-04-17 to 2026-09-22 |

The table files the five one-day moves under `parser`.

## Lessons

- A big ticket can hide more than one bug. Read the reports before you merge on subject.
- Intake's tag is a guess from the browser. Cause depends on the tenant and the booking form.

desk ref **DR-638K-A51G**
