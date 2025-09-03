# 42 Karting

<table>
  <tr>
    <td>
      <img width="300" height="300" alt="42karting-logo" src="https://github.com/user-attachments/assets/471fd527-b7fe-4167-af52-a464685eb1f0" />
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      A tiny go kart leaderboard that runs on GitHub Pages.<br>
      One TOML file per event. Events live inside a folder for each school.<br>
      Blue chip means wet conditions.
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
│ ├─ hero.jpg # banner image
│ └─ logo.svg
└─ data/
├─ events.json # list of event files
└─ 42-London/
└─ mile-end-2025-09-03.toml
```


## Set up GitHub Pages

1. Push this repo to GitHub.
2. Open Settings, then Pages.
3. Source is `main`, folder is root.
4. Wait for the green check. Your site is live.

## Data format

Each event is its own TOML file.

**Example event**

```toml
# data/42-London/mile-end-2025-09-03.toml
id = "mile-end-2025-09-03"
name = "Mile End Meetup"
venue = "London Mile End Revolution Karting"
date = "03/09/25"
school = "42 London"
conditions = "wet"

[[laps]]
username = "mila"
time = 54.238
img = "https://example.com/mila.jpg"

[[laps]]
username = "raf"
time = "00:52.901"
img = "https://example.com/raf.png"
```

### Manifest

Static hosting cannot auto list files, so we keep a small list.

```json
[
  "data/42-London/mile-end-2025-09-03.toml"
]
```

## Add a new event

1. Create a TOML file in data/<School>/<slug>.toml.

2. Add the file path to data/events.json.

3. Commit and push.

Students from other schools can add their own folder under data/ and follow the same steps.

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
