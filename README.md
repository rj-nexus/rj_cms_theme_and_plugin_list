# RJ Nexus — Theme & Plugin Registry

Official registry of themes and plugins for [RJ Nexus](https://github.com/rj-nexus/rj-nexus). RJ Nexus reads this registry from the admin panel under **Appearance → Themes → Browse** and **Plugins → Browse**.

## Structure

| File | Purpose |
|---|---|
| `registry.json` | Index with pointers, counts, and timestamps |
| `themes.json` | All approved themes |
| `plugins.json` | All approved plugins |
| `schema/` | JSON Schemas for validation |
| `index.html` | GitHub Pages submission form |
| `.github/workflows/` | CI validation and issue-to-PR automation |

## Submit a Theme or Plugin

Two ways, pick one:

### 1. Web form (recommended)

Open **https://rj-nexus.github.io/rj_cms_theme_and_plugin_list/** and fill in the form. It opens a prefilled GitHub issue. A bot validates and opens a Pull Request automatically.

### 2. Manual Pull Request

1. Fork this repository.
2. Add your entry to `themes.json` or `plugins.json` (see the relevant schema in `schema/`).
3. Update `count` and `updated_at` in `registry.json`.
4. Open a Pull Request. CI validates schema, duplicates, and your repo's manifest.

## Entry Requirements

- Repository must be **public** on GitHub.
- Repository must contain `theme.json` or `plugin.json` at its **root**.
- Manifest must have valid `name` and `version` fields.
- `name` in the manifest must match the `name` in your registry entry.
- Logos and screenshots must be direct `https://` URLs.
- Tags: lowercase, hyphen-separated, max 8.
- Category must be one from the schema enum.

## Image Hosting

No account required:
- [freeimage.host](https://freeimage.host)
- [imgbb.com](https://imgbb.com)
- [postimages.org](https://postimages.org)
- [mini-tools.uk](https://mini-tools.uk)

Any direct HTTPS URL works — GitHub raw, your own CDN, Imgur, etc.

## Review Process

1. Submission arrives as a GitHub issue.
2. Bot validates the payload and the target repo's manifest.
3. Bot opens a Pull Request with the new entry (`verified: false`, `featured: false`).
4. CI re-validates the PR.
5. Maintainers review and merge.
6. RJ Nexus clients pick up the update on next registry refresh.

`verified` and `featured` flags are set by maintainers after review.

## Schema

- [`schema/registry.schema.json`](schema/registry.schema.json)
- [`schema/theme.schema.json`](schema/theme.schema.json)
- [`schema/plugin.schema.json`](schema/plugin.schema.json)

## License

MIT
