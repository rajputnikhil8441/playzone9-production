# playzone9-production

Production deploy target for **Playzone9** → `https://www.playzone9.app`.

The site is **built from the JSK1 master** (`rajputnikhil8441/jsk1@main`) by the
GitHub Actions workflow in `.github/workflows/deploy.yml`, using the same-repo
Pages pattern (`configure-pages` + `upload-pages-artifact` + `deploy-pages`).

- This repo contains **no engine copy** — the engine, templates, brands and
  build tool are checked out from the master at build time. Do not vendor them.
- This repo contains **no `CNAME`** — the custom domain is set in this repo's
  **Settings → Pages** at cutover, not committed.
- Trigger: **manual only** (`workflow_dispatch`) for now.
- Build omits `--from-cms` until the Supabase row for `playzone9app` exists.

## Deploy (manual)
Actions → "Deploy Playzone9 (production)" → **Run workflow**. Then verify at the
repo's `*.github.io` URL before any domain cutover.
