# North Korea Administrative Divisions / 조선민주주의인민공화국



## Overview

| Item | Details |
|------|---------|
| Province | 11 |
| County | 179 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/kp](https://openadmindata.org/kp/) |
| API | [openadmindata.org/api/kp](https://openadmindata.org/api/kp/) |
| Flag | [PNG](https://onlygames.me/flags-png/kp/) · [SVG](https://onlygames.me/flags-svg/kp/) · [PDF](https://onlygames.me/flags-pdf/kp/) |
| National Anthem | [🎵 Listen & Download North Korea National Anthem MP3](https://onlygames.me/national-anthems/kp/) |

## Browse by Province

| # | Province | Countys | Link |
|---|----|----|------|
| 1 | Jagang | 18 | [Browse](divisions/jagang-kp05/) |
| 2 | Kangwon | 17 | [Browse](divisions/kangwon-kp04/) |
| 3 | Nampo | 6 | [Browse](divisions/nampo-kp11/) |
| 4 | North Hamgyong | 16 | [Browse](divisions/north-hamgyong-kp02/) |
| 5 | North Hwanghae | 21 | [Browse](divisions/north-hwanghae-kp08/) |
| 6 | North Pyongan | 25 | [Browse](divisions/north-pyongan-kp06/) |
| 7 | Pyongyang | 3 | [Browse](divisions/pyongyang-kp10/) |
| 8 | Ryanggang | 12 | [Browse](divisions/ryanggang-kp01/) |
| 9 | South Hamgyong | 20 | [Browse](divisions/south-hamgyong-kp03/) |
| 10 | South Hwanghae | 20 | [Browse](divisions/south-hwanghae-kp09/) |
| 11 | South Pyongan | 21 | [Browse](divisions/south-pyongan-kp07/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 11 province records |
| [all-county.json](data/all-county.json) | JSON | All 179 county records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['county']} countys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=county |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
```

Countys are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
North Korea Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/north-korea-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
