# Cameroon Administrative Divisions / Cameroun

Open dataset of Cameroon's administrative hierarchy — 10 regions, 58 divisions, and 360 subdivisions. This repository provides structured, bilingual (French + English) reference data with geographic coordinates at every level. Designed for developers, researchers, government agencies, and AI agents.

Licensed under CC-BY-4.0. Browse the hierarchy through GitHub's folder navigation, download aggregate files in JSON/CSV/NDJSON, or integrate directly via raw URLs.

## Overview

| Item | Details |
|------|---------|
| Region | 10 |
| Division | 58 |
| Subdivision | 360 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/cm](https://openadmindata.org/cm/) |
| API | [openadmindata.org/api/cm](https://openadmindata.org/api/cm/) |

## Browse by Region

| # | Region | Divisions | Subdivisions | Link |
|---|----|----|----|------|
| 1 | Adamaoua (Adamawa) | 5 | 21 | [Browse](divisions/adamawa-cm001/) |
| 2 | Centre | 10 | 70 | [Browse](divisions/centre-cm002/) |
| 3 | Est (East) | 4 | 33 | [Browse](divisions/east-cm003/) |
| 4 | Extrême-Nord (Far-North) | 6 | 47 | [Browse](divisions/far-north-cm004/) |
| 5 | Littoral | 4 | 34 | [Browse](divisions/littoral-cm005/) |
| 6 | Nord (North) | 4 | 21 | [Browse](divisions/north-cm006/) |
| 7 | Nord-Ouest (North-West) | 7 | 34 | [Browse](divisions/north-west-cm007/) |
| 8 | Sud (South) | 4 | 29 | [Browse](divisions/south-cm009/) |
| 9 | Sud-Ouest (South-West) | 6 | 31 | [Browse](divisions/south-west-cm010/) |
| 10 | Ouest (West) | 8 | 40 | [Browse](divisions/west-cm008/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 10 region records |
| [all-division.json](data/all-division.json) | JSON | All 58 division records |
| [all-subdivision.json](data/all-subdivision.json) | JSON | All 360 subdivision records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['division']} divisions")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=division, 3=subdivision |
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
divisions/{region-slug}/
divisions/{region-slug}/{division-slug}/
```

Subdivisions are listed inline in each division's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Cameroon Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/cameroon-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
