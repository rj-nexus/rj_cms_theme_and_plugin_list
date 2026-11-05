<div align="center">

# RJ Nexus — Theme & Plugin Registry

The official registry of themes and plugins for [RJ Nexus](https://github.com/rj-nexus/rj-nexus).

<br>

<a href="https://rj-nexus.github.io/rj-registration/">
  <img src="https://img.shields.io/badge/Submit%20Now-Open%20Web%20Form-7c3aed?style=for-the-badge&logo=github" alt="Submit Theme or Plugin">
</a>

<br>
<br>

<sub>No fork and no JSON editing. Fill in the form and a bot opens the Pull Request for you.</sub>

<br>
<br>

![Themes](https://img.shields.io/badge/themes-registry-3b82f6?style=flat-square)
![Plugins](https://img.shields.io/badge/plugins-registry-6366f1?style=flat-square)
![Review](https://img.shields.io/badge/review-1--7%20days-22d3ee?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-8b5cf6?style=flat-square)

</div>

---

## Overview

RJ Nexus reads this registry from the admin panel:

- **Appearance → Themes → Browse**
- **Plugins → Browse**

Anything merged here becomes available to every RJ Nexus installation on its next registry refresh.

```mermaid
flowchart LR
    A[Web form] --> B[GitHub issue]
    B --> C[Bot validates]
    C --> D[Pull Request]
    D --> E[Maintainer review]
    E --> F[Live in RJ Nexus]
```

---

## Submit a theme or plugin

### Option 1: Web form (recommended)

<div align="center">

<a href="https://rj-nexus.github.io/rj-registration/">
  <img src="https://img.shields.io/badge/Open%20Submission%20Form-rj--nexus.github.io-ec4899?style=for-the-badge&logo=github" alt="Open Submission Form">
</a>

</div>

1. Open the form and fill in the fields.
2. Click **Continue on GitHub**. A prefilled issue opens.
3. Click **Submit new issue**.
4. A bot validates the submission and opens a Pull Request automatically.

### Option 2: Manual Pull Request

1. Fork this repository.
2. Add your entry to `themes.json` or `plugins.json` (see the matching schema in `schema/`).
3. Update `count` and `updated_at` in `registry.json`.
4. Open a Pull Request. CI validates the schema, duplicates, and your repository manifest.

> [!TIP]
> Full step-by-step instructions, ZIP rules, and entry examples are in [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Entry requirements

| Requirement | Details |
|---|---|
| Repository | Must be **public** on GitHub |
| Manifest | `theme.json` or `plugin.json` at the repository **root** |
| Manifest fields | Valid `name` and `version` |
| Name match | Manifest `name` must match the registry entry `name` |
| Images | Logos and screenshots must be direct `https://` URLs |
| Tags | Lowercase, hyphen-separated, max 8 |
| Category | Must be a value from the schema enum |

---

## Image hosting

No account is required for these services:

| Service | Link |
|---|---|
| freeimage.host | https://freeimage.host |
| imgbb | https://imgbb.com |
| postimages | https://postimages.org |
| mini-tools | https://mini-tools.uk |

Any direct HTTPS URL also works: GitHub raw, your own CDN, Imgur, and so on.

---

## Review process

| Step | What happens |
|---|---|
| 1 | The submission arrives as a GitHub issue |
| 2 | The bot validates the payload and the target repository manifest |
| 3 | The bot opens a Pull Request with the new entry (`verified: false`, `featured: false`) |
| 4 | CI validates the Pull Request again |
| 5 | Maintainers review and merge |
| 6 | RJ Nexus clients pick up the update on the next registry refresh |

> [!NOTE]
> The `verified` and `featured` flags are set by maintainers after review.

---

## Repository structure

| File | Purpose |
|---|---|
| `registry.json` | Index with pointers, counts, and timestamps |
| `themes.json` | All approved themes |
| `plugins.json` | All approved plugins |
| `schema/` | JSON Schemas used for validation |
| `index.html` | GitHub Pages submission form |
| `.github/workflows/` | CI validation and issue-to-PR automation |

### Schemas

- [`schema/registry.schema.json`](schema/registry.schema.json)
- [`schema/theme.schema.json`](schema/theme.schema.json)
- [`schema/plugin.schema.json`](schema/plugin.schema.json)

---

## License

Released under the [MIT License](LICENSE).

<div align="center">

<br>

<a href="https://rj-nexus.github.io/rj-registration/">
  <img src="https://img.shields.io/badge/Ready%3F-Submit%20your%20package-7c3aed?style=for-the-badge" alt="Submit your package">
</a>

</div>
