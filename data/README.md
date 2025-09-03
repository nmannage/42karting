# Data

All leaderboard data lives here.

## Event files

Each event is one TOML file.

- Path: `data/<school-slug>/<venue-slug>-<yyyy-mm-dd>.toml`
- `id`: `<venue-slug>-<yyyy-mm-dd>`
- `date`: `DD/MM/YY`
- Add the path to `data/events.json`

**Example path**

```
data/42-London/42-karting-hq-2025-09-03.toml
```

**Example id**

```
id = "42-karting-hq-2025-09-03"
```

## Slugs and names

- Slugs: lowercase, hyphens, ASCII. Example: `42-karting-hq`
- `venue`: short display name. Add city only if needed to disambiguate
- `name`: human friendly event name

## Images

- Venue: `assets/venues/<venue-slug>.jpg`
- Track: `assets/tracks/<venue-slug>-layout.png`
- Avatars: `assets/avatars/<username>.jpg`
- Fallbacks are used if images are missing

## Manifest

`data/events.json` lists all event files. Example:
```json
[
  "data/42-London/42-karting-hq-2025-09-03.toml"
]
```

## Branch and PR naming
### Branch name

- For a new event:
```
event/<yyyy-mm-dd>-<school-slug>-<venue-slug>
```
```
event/2025-09-03-42-london-42-karting-hq
```

## PR title

```
Add event: <School> @ <Venue> (<DD/MM/YY>)`
```

```
Add event: 42 London @ 42 Karting HQ (03/09/25)
```




