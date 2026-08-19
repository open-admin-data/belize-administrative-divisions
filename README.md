# Belize Administrative Divisions / Belize



## Overview

| Item | Details |
|------|---------|
| District | 6 |
| Locality | 462 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/bz](https://openadmindata.org/bz/) |
| API | [openadmindata.org/api/bz](https://openadmindata.org/api/bz/) |
| National Anthem | [🎵 Listen & Download Belize National Anthem MP3](https://onlygames.me/national-anthems/bz/) |

## Browse by District

| # | District | Localitys | Link |
|---|----|----|------|
| 1 | Belize | 54 | [Browse](divisions/belize-bz01/) |
| 2 | Cayo | 120 | [Browse](divisions/cayo-bz02/) |
| 3 | Corozal | 67 | [Browse](divisions/corozal-bz03/) |
| 4 | Orange Walk | 83 | [Browse](divisions/orange-walk-bz04/) |
| 5 | Stann Creek | 50 | [Browse](divisions/stann-creek-bz05/) |
| 6 | Toledo | 88 | [Browse](divisions/toledo-bz06/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-district.json](data/all-district.json) | JSON | All 6 district records |
| [all-locality.json](data/all-locality.json) | JSON | All 462 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-district.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['locality']} localitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-district.json", "utf-8"));
console.log(`Total: ${data.length} districts`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=district, 2=locality |
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
divisions/{district-slug}/
```

Localitys are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-district links
- [Per-district data](docs/llms-full/) — Full data by district

## Citation

```
Belize Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/belize-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
