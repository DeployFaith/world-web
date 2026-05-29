# Content format

## registry.json

Top-level fields:
- `version` (integer)
- `product` (string)
- `default_domain` (string)
- `sites` (array)

Each `sites[]` item:
- `domain` (string, lowercase, `.hermes`)
- `title` (string)
- `description` (string)
- `root` (string, repo-relative path like `sites/home.hermes`)
- `entry` (string route, usually `/`)
- `routes` (object mapping route path -> file path under site root)
- `agent_visible` (boolean)

Example route mapping:

```json
"routes": {
  "/": "pages/index.html",
  "/about": "pages/about.html"
}
```

## site.json

Location:
- `sites/<domain>/site.json`

Fields:
- `domain`
- `title`
- `description`
- `entry`
- `routes`
- `agent_visible`

Notes:
- `site.json` `domain` must match the `registry.json` entry domain.
- Route keys must start with `/`.
- Route targets must stay inside that site root.
- Route targets must be static files (no HTTP/localhost targets).
