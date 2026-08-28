# Henderson Astronomy — astro.thgnetworks.com

The hub / front door for Aaron Henderson's astronomy work. Links out to the
individual project sites on their own subdomains; carries no content of its own
beyond the map and a short about.

**Personal site.** Not a THG Media property.

## The family

| Subdomain | What it is | Repo | Status |
|-----------|------------|------|--------|
| `astro.thgnetworks.com` | this hub | `thg4web/astro` | in build |
| `luna.thgnetworks.com` | USGS Geologic Atlas of the Moon, interactive | `thg4web/luna` | live |
| `mmol.thgnetworks.com` | Messier Marathon Observer's Log | `thg4web/mmol` | live |
| `images.thgnetworks.com` | astrophotography gallery | — | planned |

## Build

Plain static HTML. No build step, no dependencies. Matches Luna and MMOL.

- `index.html` — the page
- `assets/styles.css` — shared skin for the astronomy family
  - Display: **Audiowide** · Body/UI: **Exo 2** · Mono: **IBM Plex Mono** (Google Fonts)
  - Accent: **#2F78BD**
  - Dark ground, light/dark theme via `prefers-color-scheme` + a toggle
- `CNAME` — `astro.thgnetworks.com` (must stay committed)

## Preview

```
./start_webserver.sh      # http://localhost:8899
```

## Deploy

GitHub Pages on `thg4web/astro`, `main` / root. Custom domain `astro.thgnetworks.com`
(ZoneEdit `CNAME` → `thg4web.github.io`), enforce HTTPS after propagation.

Commit auth: `source ../git_info/git-auth-thg.sh` (a dedicated `git-auth-astro.sh`
+ deploy key to follow).
