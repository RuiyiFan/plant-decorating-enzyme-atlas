# API (static)

- `GET records.json` — all 1451 records as JSON (array under `records`).
- `GET index.json` — metadata (version, counts, licence).

There is no server-side query API. Filter client-side, e.g.:

```js
const d = await (await fetch('records.json')).json();
const hits = d.records.filter(r => r.tier === 'A' && r.position === '3-O');
```

Fields mirror `exports/atlas_v0.10_full.tsv`. Tier A/B records carry `quote` and `text_offset`
(character offset into the corresponding PMC full text).

Licence: CC BY 4.0.
