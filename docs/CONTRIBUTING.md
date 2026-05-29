# Contributing

## Add a site

1. Create `sites/<domain>/`.
2. Add `sites/<domain>/site.json`.
3. Add route files (for example `pages/index.html`) and optional static assets (for example `styles/site.css`).
4. Add/update the domain entry in `registry.json`:
   - `domain`
   - `root`
   - `entry`
   - `routes`
   - metadata fields

## Add routes

1. Add a route key in `routes` that starts with `/`.
2. Point it to a file path under the site root.
3. Create the target file.

Example:

```json
"routes": {
  "/": "pages/index.html",
  "/about": "pages/about.html"
}
```

## Validate

Run:

```bash
python3 tools/validate_world_web.py
```

Validation must pass before opening or merging a PR.

## Content safety rules

- Static local content only.
- No remote trackers.
- No analytics beacons.
- No injected third-party scripts.
- No localhost links or dependencies.
- Keep assets reasonably small.
- Do not leave placeholder domains:
  - `news.grid`
  - `atlas.node`
  - `vault.corp`
