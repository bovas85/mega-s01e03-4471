<script lang="ts">
  import reports from '#lib/data/reports-4471.json';
  import notes from '#lib/data/desk-notes.json';
  import { causeOf, uniqueById, type Report } from '#lib/kb/causes';
  import { tenantOf } from '#lib/kb/locales';

  let { ticket }: { ticket: number } = $props();

  // One id, one report. A one-day move is its own problem, whatever the tenant's cause says.
  const merged = $derived(uniqueById(reports as Report[]).filter((r) => r.mergedInto === ticket));
  const oneDay = $derived(merged.filter((r) => notes.oneDayMove.includes(r.id)));
  const rest = $derived(merged.filter((r) => !notes.oneDayMove.includes(r.id)));
  const count = (c: string) => rest.filter((r) => causeOf(r, tenantOf(r)) === c).length;
  const rows = $derived([
    { problem: 'parser', what: 'shared parser reads dates month first', n: count('parser') },
    { problem: 'hint', what: 'booking-v3 form hint says MM/DD/YYYY to day-first tenants', n: count('hint') },
    { problem: 'one-day move', what: 'date is exactly one day off, month not flipped', n: oneDay.length },
  ]);
</script>

<table>
  <thead><tr><th>problem</th><th>what</th><th>reports</th></tr></thead>
  <tbody>
    {#each rows as row (row.problem)}
      <tr><td><code>{row.problem}</code></td><td>{row.what}</td><td>{row.n}</td></tr>
    {/each}
  </tbody>
  <tfoot><tr><td colspan="2">merged into #{ticket}</td><td>{merged.length}</td></tr></tfoot>
</table>
