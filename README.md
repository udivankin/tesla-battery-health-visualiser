# Tesla Battery Health Visualiser

An interactive visualisation of Tesla battery degradation, built from a
[Tessie](https://tessie.com) battery-health CSV export. Single self-contained
HTML file — pure SVG rendering, animated with [GSAP](https://gsap.com) (loaded
from CDN).

**Live:** https://udivankin.github.io/tesla-battery-health-visualiser/

## Features

- Smoothed capacity curve with a soft glow and gradient, raw readings as dots,
  drawn in with a sweep animation; switching axis modes morphs the curve
- Battery health, usable capacity, max range, odometer and degradation-trend
  stat tiles computed from the data
- Switch the x-axis between **odometer** and **time**
- Distance unit toggle — **km (default) or mi** — converting from whichever
  unit the CSV was exported in
- Dashed trend projection based on the most recent half of the mileage span
- Crosshair + tooltip on hover with date, health %, capacity, range and odometer
- Peak and outlier readings called out with leader-line annotations
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
