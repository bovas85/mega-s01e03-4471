# #4471 - three problems, not one

owner **Leelium** | status **resolved** | reviewed 2026-10-28

[#4471](/kb/incidents/4471) merged 412 reports as one issue. Read one by one, they are three different problems.

> Resolved on 05 Oct: parser fixed (`fix(dates): parse dd/mm for eu locales`), hint won't fix (`booking-v3 form retired`).

## The three problems

| problem | what | reports |
|---|---|---|
| `parser` | shared parser reads dates month first | 379 |
| `hint` | booking-v3 form hint says MM/DD/YYYY to day-first tenants | 33 |
| `one-day move` | date is exactly one day off, month not flipped (filed under parser) | 5 |
| | merged into #4471 | **412** |

1. **parser** - fixed: `fix(dates): parse dd/mm for eu locales`.
2. **hint** - won't fix: `booking-v3 form retired`.
3. **one-day move** - R-41202, R-41209, R-41236, R-41344, R-41620. Filed under parser in desk table.

## What the desk table says

| cause | reports | tagged as | tenants | seen |
|---|---|---|---|---|
| `parser` | 379 | parser 356, hint 23 | 11 | 2026-04-01 to 2026-10-04 |
| `hint` | 33 | hint 18, parser 15 | 3 | 2026-04-17 to 2026-09-22 |

The table files the five one-day moves under `parser`.

## Lessons

- A big ticket can hide more than one bug. Read the reports before you merge on subject.
- Intake's tag is a guess from the browser. Cause depends on the tenant and the booking form.

desk ref **DR-K354-PXMA**
