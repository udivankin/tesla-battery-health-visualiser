# Tesla Battery Health Visualiser

An interactive 3D visualisation of Tesla battery degradation, built from a
[Tessie](https://tessie.com) battery-health CSV export. Single self-contained
HTML file rendered with [Three.js](https://threejs.org) (loaded from CDN).

**Live:** https://udivankin.github.io/tesla-battery-health-visualiser/

## Features

- Glowing 3D capacity curve (smoothed) with raw readings as points, drawn in
  with an intro animation
- Battery health, usable capacity, max range, odometer and degradation-trend
  stat tiles computed from the data
- Switch the x-axis between **odometer** and **time**
- Distance unit toggle — **km (default) or mi** — converting from whichever
  unit the CSV was exported in
- Dashed trend projection based on the most recent half of the mileage span
- Hover any reading for date, health %, capacity, range and odometer
- Flat front-on chart with pointer parallax; the third dimension is reserved
  for annotation pins that lift the peak and outlier readings off the plane
- **Drag & drop your own Tessie CSV** (or use the Load CSV button) — everything
  recomputes client-side; no data leaves your browser

## Using your own data

In Tessie: **Battery health → Export CSV**, then drop the file onto the page.
Expected columns: `Timestamp`, `Odometer (mi|km)`, `Max Range`, `Usable Capacity (kWh)`.
Health % is measured against the peak smoothed capacity in the export.

## Development

It's one file — open `index.html` via any static server, e.g.:

```sh
npx http-server -p 8734
```

## Deployment

Hosted on GitHub Pages, served from the `main` branch root.
