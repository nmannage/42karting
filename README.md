# 42 Karting

<table>
  <tr>
    <td>
      <img width="300" height="300" alt="42karting-logo" src="https://github.com/user-attachments/assets/471fd527-b7fe-4167-af52-a464685eb1f0" />
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      A tiny go kart leaderboard that runs on GitHub Pages.<br>
      One TOML file per event. Events live inside a folder for each school.<br>
    </td>
  </tr>
</table>

## What you get

- Static site with no backend
- Global leaderboard with School, Venue, and Event filters
- Venue records for the current filter
- Super easy pull requests for new events

## Project structure

```bash
.
├─ index.html
├─ assets/
│  ├─ hero.jpg        # banner image (or hero.png or hero.svg)
│  ├─ logo.svg
│  └─ fallbacks/
│     ├─ hero-fallback.svg
│     ├─ avatar.svg
│     ├─ venue.svg
│     └─ track.svg
└─ data/
   ├─ events.json     # list of event files
   └─ 42-London/
      └─ 42-karting-hq-2025-09-03.toml
```


## Set up GitHub Pages

1. Push this repo to GitHub.
2. Open Settings, then Pages.
3. Source: main, folder: root.

## Images

The hero tries assets/hero.jpg, then assets/hero.png, then assets/hero.svg. If none exist it shows a fallback.
Any image in TOML can be a repo path like assets/... or a full URL.
Fallbacks live in assets/fallbacks/.

## Data format

Each event is its own TOML file. Define drivers once, then list races with entries that reference those drivers.

**Example event**

```toml
# data/42-London/42-karting-hq-2025-09-03.toml
id = "42-karting-hq"
name = "42KartingHQ"
venue = "20 Whitechapel"
date = "03/09/25"
school = "42 London"
conditions = "wet"                # overall event condition (optional)
venue_img = "assets/venues/42-karting-hq.jpg"
track_img = "assets/tracks/42-karting-hq-layout.png"

# drivers are defined once
[[drivers]]
username = "gigi"
img = "assets/avatars/gigi.jpg"

[[drivers]]
username = "nmannage"
img = "assets/avatars/nmannage.jpg"

[[drivers]]
username = "moulinette"
img = "assets/avatars/moulinette.jpg"

[[drivers]]
username = "norminette"
img = "https://example.com/avatars/norminette.png"

# multiple races in the same event
[[races]]
id = "heat-1"
name = "Heat 1"
laps = 12
conditions = "dry"

  [[races.entries]]
  user = "gigi"
  laptime = 53.782                 # seconds or "mm:ss.mmm"

  [[races.entries]]
  user = "nmannage"
  laptime = "00:54.210"

  [[races.entries]]
  user = "moulinette"
  laptime = 55.004

  [[races.entries]]
  user = "norminette"
  laptime = "00:56.199"

[[races]]
id = "heat-2"
name = "Heat 2"
laps = 10
conditions = "wet"

  [[races.entries]]
  user = "gigi"
  laptime = "00:52.991"

  [[races.entries]]
  user = "nmannage"
  laptime = 53.333

  [[races.entries]]
  user = "moulinette"
  laptime = "00:54.879"

  [[races.entries]]
  user = "norminette"
  laptime = 55.320

[[races]]
id = "final"
name = "Final"
laps = 15
conditions = "wet"

  [[races.entries]]
  user = "gigi"
  laptime = 53.450

  [[races.entries]]
  user = "nmannage"
  laptime = "00:52.870"

  [[races.entries]]
  user = "moulinette"
  laptime = 54.620

  [[races.entries]]
  user = "norminette"
  laptime = "00:55.905"

```

### Manifest

Static hosting cannot auto list files, so we keep a small list.

```json
[
  "data/42-London/mile-end-2025-09-03.toml"
]
```

## Add a new event

1. Create `data/<School>/<slug>.toml` using the example format.

2. Add the file path to `data/events.json`.

3. Commit and push.

Students from other schools can add their own folder under `data/` and follow the same steps.

### Local preview

Open a simple static server, then visit the URL.

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Contributing

Pull requests are welcome.
Please keep changes small and focused.
If you add an event file, remember to update data/events.json.
