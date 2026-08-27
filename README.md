# Aldo Orvieto — GitHub Pages website

A complete bilingual Jekyll site with no JavaScript, framework, theme, database, CMS, external font, animation, or build dependency beyond GitHub Pages itself.

## What visitors see now

The public root page:

```text
https://YOUR-ADDRESS/
```

shows only:

```text
Aldo Orvieto
Pianista
Sito in preparazione
```

There is no visible link to the complete website.

## Hidden preview address

Open the complete Italian site by adding:

```text
/studio/
```

For example:

```text
https://YOUR-USERNAME.github.io/studio/
```

The English version is:

```text
https://YOUR-USERNAME.github.io/studio/en/
```

The preview pages contain `noindex` metadata and `robots.txt` asks search engines not to crawl `/studio/`. This is useful for an unpublished preview, but it is **not password protection**: anyone who knows the URL can open it.

## Structure

```text
aldo-orvieto-github-pages/
├── index.md                         # public work-in-progress page
├── studio/                          # complete hidden preview site
│   ├── index.md                     # Italian home
│   ├── biografia.md
│   ├── concerti.md
│   ├── discografia.md
│   ├── attivita.md
│   ├── progetti.md
│   ├── prime-esecuzioni.md
│   ├── ricerca.md
│   ├── pubblicazioni.md
│   ├── stampa.md
│   ├── contatti.md
│   └── en/                          # complete English version
├── _includes/
│   ├── discography-list.md          # all 101 releases, shared by IT and EN
│   ├── head.html
│   ├── header.html
│   └── footer.html
├── _layouts/
├── assets/
│   ├── css/style.css
│   └── images/aldo-portrait.jpg
├── _config.yml
├── robots.txt
├── 404.md
├── HOW-ALDO-UPDATES.md
├── CONTENT-SOURCES.md
└── README.md
```

## Upload to GitHub

The simplest repository name is exactly:

```text
YOUR-GITHUB-USERNAME.github.io
```

1. Create that public repository on GitHub.
2. Unzip this folder.
3. Open the empty GitHub repository.
4. Choose **Add file → Upload files**.
5. Upload everything **inside** `aldo-orvieto-github-pages` so that `_config.yml`, `index.md`, `studio`, `_layouts`, and `assets` are directly at the repository root.
6. Commit the files.
7. Open **Settings → Pages**.
8. Under **Build and deployment**, select **Deploy from a branch**, then `main` and `/(root)`.
9. Wait for the Pages deployment to complete.

Temporary public page:

```text
https://YOUR-GITHUB-USERNAME.github.io/
```

Hidden complete preview:

```text
https://YOUR-GITHUB-USERNAME.github.io/studio/
```

## Using a project repository instead

When the repository is not named `USERNAME.github.io`, its temporary URL includes the repository name. Set this in `_config.yml`:

```yaml
baseurl: "/REPOSITORY-NAME"
```

All internal assets and navigation use Jekyll’s `relative_url`, so they will continue to work.

## Updating content

Aldo normally edits only Markdown:

- `studio/concerti.md`
- `studio/biografia.md`
- `studio/progetti.md`
- `studio/prime-esecuzioni.md`
- `studio/ricerca.md`
- `studio/pubblicazioni.md`
- `studio/stampa.md`
- `studio/contatti.md`
- the equivalent files in `studio/en/`
- `_includes/discography-list.md` for the complete discography

Full instructions are in `HOW-ALDO-UPDATES.md`.

## Replacing the portrait

Replace:

```text
assets/images/aldo-portrait.jpg
```

with an authorised vertical photograph using the same filename. A 4:5 image around 1600 × 2000 pixels is ideal.

## Making the complete site public later

The current separation is deliberate: root = work in progress, `studio/` = preview.

For launch, the cleanest method is:

1. Delete or rename the current root `index.md`.
2. Move the contents of `studio/` to the repository root.
3. Move `studio/en/` to `/en/`.
4. In `_config.yml`, remove `/studio` from every navigation URL.
5. Update the `permalink` and `alternate_url` values in the Markdown front matter by removing `/studio`.
6. Remove `noindex: true` from the public pages.
7. Remove the `/studio/` rule from `robots.txt`.

Until then, keep the folder structure unchanged.

## Design

The design is intentionally quiet: a large monochrome portrait, editorial serif typography, a compact uppercase navigation, fine rules, generous whitespace, and no animated behaviour. It draws only broad inspiration from the restraint and photographic emphasis of the Nelson Goerner site and the direct section-based simplicity of the Enrico Bronzi site.
