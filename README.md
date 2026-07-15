# Byron Expansion Dashboard

Single-file dashboard tracking Roofing Down Under's relocation to the Northern NSW corridor (Byron Bay → QLD border). Seven pillars: milestones, subbie prospecting (incl. trades/services to source), builder pipeline, networking, team recruitment, marketing setup, and social foundations.

No accounts, no login, no server — everything saves automatically in your browser (localStorage).

## Deploy (Netlify)

In Netlify: *Add new site → Import an existing project → GitHub → pick this repo*. Leave the build command empty — the included `netlify.toml` publishes the repo root, no build step. Every push then auto-deploys.

## How data works

- Ticks and counters save instantly; text fields save half a second after you stop typing. A "Saved ✓" toast confirms each save.
- Data is stored **per device/browser** — your phone and laptop each have their own copy.
- Use **Backup** (header button) to download a JSON file of the board, and **Restore** to load it on another device or after clearing your browser. Worth taking a backup now and then.
