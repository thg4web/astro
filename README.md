# Henderson Astronomy — astro.thgnetworks.com

The hub / front door for Aaron Henderson's astronomy work. Links out to the
individual project sites on their own subdomains; carries no content of its own
beyond the map and a short about.

**Personal site.** Not a THG Media property.

Live: <https://astro.thgnetworks.com>

## The family

| Subdomain | What it is | Repo | Status |
|-----------|------------|------|--------|
| `astro.thgnetworks.com` | this hub | `thg4web/astro` | live |
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
- `assets/andromeda.jpg` — fixed full-bleed M31 (Andromeda) background, Aaron's own
  shot, web-optimised. On the light theme it renders as a bright grayscale negative.
- `assets/pleiades.png` — masthead Pleiades asterism (drawn via CSS mask so it takes
  the accent colour), linked to Wikipedia with a "For my Love" tooltip.
- A small `<canvas>` starfield twinkles behind the content in both themes; it honours
  `prefers-reduced-motion`.
- `CNAME` — `astro.thgnetworks.com` (must stay committed)
- `.nojekyll` — serve files as-is

The hero treatment (background photo + starfield + asterism) is adapted from the
`www.thgnetworks.com` landing page, retuned to this blue skin.

## Preview

```
./start_webserver.sh      # http://localhost:8899
```

## Deploy

GitHub Pages on `thg4web/astro`, `main` / root. Custom domain `astro.thgnetworks.com`
(ZoneEdit `CNAME` → `thg4web.github.io`), Enforce HTTPS on. Pushes to `main` redeploy
automatically.

Commit auth: `source ../git_info/git-auth-astro.sh` (the `id_astro` deploy key).
The auth script's final `ssh -T` exits non-zero and shell env does not persist
between separate invocations, so push in one line:

```
source ../git_info/git-auth-astro.sh; git push
```

## Not committed

`Project/` (kickoff minutes, change log, action items, document index) and
`start_webserver.sh` are gitignored — local working files only, never published.
Time Machine is version control for those.
