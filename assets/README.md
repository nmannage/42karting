# Assets

This folder holds images used by the site. You can use file paths from here or full URLs in your TOML files.

## Structure

```
assets/
hero.jpg # banner image for the top of the page
logo.svg # site logo
avatars/ # driver profile photos
venues/ # venue photos
tracks/ # track layout images
```

## File naming

- Keep names simple and lowercase
- Use hyphens between words
- Examples
  - `avatars/gigi.jpg`
  - `venues/42-karting-hq.jpg`
  - `tracks/42-karting-hq-layout.png`

## Recommended sizes

- `hero.jpg` around 1920x600
- `logo.svg` preferred. PNG works too
- Avatars around 256x256
- Venue photos around 1600x900
- Track layouts can be PNG or SVG. SVG is nice if you have it

## How to reference images

In your event TOML you can use a repo path or a full URL.

```toml
img = "assets/avatars/gigi.jpg"
venue_img = "assets/venues/42-karting-hq.jpg"
track_img = "https://example.com/layout.png"
```

### Note

- Keep files small for faster load
- Use JPG for photos and PNG or SVG for graphics and layouts
- If you change a filename, update the TOML that points to it
