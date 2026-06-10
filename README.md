# The Periodic Table of Robotics

86 elements covering the topics, skills and areas of robotics, presented as
a chemistry-style periodic table at `/periodic-table/`.

## How it fits together

- **`/web/_data/periodic_table.yml`** — the single source of truth: every
  element's two-letter code, name, atomic number, grid position, category
  and tags. Categories (and their colours) are defined at the top.
- **`/web/_ptor/<slug>.md`** — one page per element (slug = lowercase
  code, e.g. `ar.md` for Arduino). Published at
  `/periodic-table/<slug>.html` via the `ptor` collection.
- **`/web/_layouts/ptor.html`** — element page layout: hero tile, related
  elements ("Reacts well with"), category siblings, tag-matched related
  articles/courses, share buttons and prev/next navigation.
- **`/web/_includes/periodic_table.html`** — renders the table grid from
  the data file.
- **`/web/assets/css/ptor.css`** — table + element page styles. Category
  colours are duplicated here (CSS custom properties) — keep in sync with
  the data file.
- **`/generate_ptor_og.py`** (repo root) — generates the per-element
  social-share images in `/web/assets/img/ptor/og/`. Re-run after adding
  or changing elements.

## Adding a new element

1. Add it to `_data/periodic_table.yml` with a UNIQUE two-letter code and
   a free grid position (rows 1-6 are the main table, row 8 is the
   detached robots row).
2. Create `_ptor/<slug>.md` — copy an existing page for the frontmatter
   shape; `number`, `code`, `name` and `category` must match the data file.
3. Run `python3 generate_ptor_og.py` to create its share image.
