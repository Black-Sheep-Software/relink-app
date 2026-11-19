# ReLink

**Your controller has more games to play.**

ReLink is a Windows/Linux Bridge for the Google Stadia Controller — one
dependable controller experience over USB cable, Bluetooth, and the
controller's native Wi-Fi radio, so a controller that would otherwise be
e-waste keeps working with the games on your computer.

🔗 the live site — domain to be added here once confirmed
📦 **[Releases](https://github.com/Black-Sheep-Software/relink-app/releases)** — download the Bridge
🐛 **[Issues](https://github.com/Black-Sheep-Software/relink-app/issues)** — bug reports and feature requests

## What this repo is

This repo holds ReLink's **public-facing website and release downloads**
only. It does not contain the Bridge's source code, which is developed in a
private repository — this keeps the public download/support surface small
and separate from in-progress engineering and hardware research.

- `index.html`, `styles.css`, `script.js`, and the image/SVG assets: the
  live site's source.
- Tagged [Releases](https://github.com/Black-Sheep-Software/relink-app/releases):
  built, installable packages for end users.

## Status

Early. USB and Bluetooth controller input work reliably. Native Wi-Fi — the
controller's own wireless radio, with no cable or re-pairing dance once set
up — is working end to end against real hardware and under active
development. A Windows build is planned but not yet implemented. See the
[Releases](https://github.com/Black-Sheep-Software/relink-app/releases)
page for what's actually downloadable today.

## Reporting a problem

Please use [Issues](https://github.com/Black-Sheep-Software/relink-app/issues)
on this repo. Include your OS, how the controller is connected
(USB/Bluetooth/Wi-Fi), and what you expected versus what happened.

## Developing the website locally

```sh
python3 -m http.server 8000
```

Open http://localhost:8000. Pushing to this repo's default branch does not
automatically redeploy the live site unless Vercel's Git integration is
connected directly to this repo (recommended, now that the site has its own
repo) — see the project's Vercel dashboard.
