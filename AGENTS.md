# AGENTS.md — Aldo Orvieto website

Bilingual (IT default, EN) Jekyll site for GitHub Pages. No JavaScript, framework, theme, or build dependency beyond GitHub Pages itself.

## Build & verify

- Jekyll is installed globally (Homebrew Ruby 4.0); there is intentionally no Gemfile.
- `jekyll build` — verify changes; must complete without errors.
- `jekyll serve` — local preview at `http://localhost:4000/`.
- Build output `_site/` and `.jekyll-cache/` are gitignored; never commit them.

## Structure

- `index.md` — public root page, a deliberate work-in-progress placeholder (layout `wip`). Not linked to the preview.
- `studio/` — the complete hidden preview site. Keep this folder structure until launch (see "Making the complete site public later" in `README.md`).
- `studio/en/` — English version. Every Italian page must have an English counterpart (and vice versa); when editing one, update the other.
- `_includes/discography-list.md` — the full discography, shared by both `studio/discografia.md` and `studio/en/discography.md`. Edit in one place only. Each label section is a collapsible `<details class="discography-section">` block; the continuous 1–101 numbering is produced by CSS counter offsets in `assets/css/style.css` (`.discography-section:nth-of-type(N)`) — update the offsets there when adding/removing entries. The "Integrali pianistiche / Complete Piano Works" section lives in the two page files themselves (customer request, Aug 2026) — keep IT and EN in sync.
- `_layouts/`, `_includes/` (head/header/footer), `assets/css/style.css` — single design system.

## Front matter conventions (see `studio/biografia.md` for a model)

- Every content page: `layout: page`, `lang` (`it`/`en`), `title`, `permalink`, `alternate_url` (the counterpart page), `noindex: true` while the site is in preview.
- Navigation lives in `_config.yml` (`navigation_it` / `navigation_en`), not in page files.
- All internal links and assets must use Jekyll's `relative_url` so a `baseurl` keeps working.

## Content conventions

- Italian is the source of truth; English mirrors it.
- Discography entries must preserve supplied titles, credits, labels, and catalogue references (see `CONTENT-SOURCES.md`).
- Contact email and social links are set in `_config.yml`, not hardcoded in pages.

## Deploy

Push to `main`; GitHub Pages builds automatically. Do not run local GitHub Actions or add CI.
