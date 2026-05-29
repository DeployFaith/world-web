# world-web

World Web is the content repository for Hermes Internet.

Hermes Internet is bundled/local fake internet content for Hermes_OS. It is static content loaded from files and does not require Docker, localhost, sidecars, or servers.

Current official site:
- `home.hermes`

Structure:
- `registry.json` maps domains and routes.
- `sites/<domain>/` stores site content.
- `system/not_found.html` is the fallback template.

Validate:

```bash
python3 tools/validate_world_web.py
```
