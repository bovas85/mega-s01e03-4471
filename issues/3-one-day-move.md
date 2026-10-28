Reports covered: **5** of the 412 in #4471.

Five reports describe a date that is exactly one day off. The month is not flipped, so this is not the parser or the hint problem. The desk already lists them in `desk-notes.json` as `oneDayMove`.

| id | tenant | what they said |
|---|---|---|
| R-41202 | kettle.books | Invite says Tuesday 12 May, calendar says Monday 11 May |
| R-41209 | alder.physio | Every booking in June is one day off. Only June |
| R-41236 | nine.lanterns | The invite arrived before the booking was made |
| R-41344 | pale.harbour | Lisbon client got Tuesday, Toronto client got Monday, same meeting |
| R-41620 | lantern.row | Tuesday 6 October showed as Monday |

Suspected cause: time zone or DST handling. Only 5 reports, so this is a suspicion, not a finding.

The desk's cause table files these under `parser` and footnotes them.

Page: src/routes/kb/incidents/4471-three-problems/+page.svx
