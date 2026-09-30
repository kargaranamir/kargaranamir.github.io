# Personal Webpage with al-folio Theme

The repository contains the personal website for [Amir Hossein Kargaran](https://kargaranamir.github.io/).

## al-folio

The website is powered by Jekyll with the [al-folio](https://github.com/alshedivat/al-folio/) theme (v1.x: a thin starter; layouts, includes and styles come from the `al_*` gems pinned in `Gemfile`).

## Notes for editing (humans and agents)

- **Publishing:** push to `main`. `.github/workflows/deploy.yml` builds the site and publishes it to the `gh-pages` branch. `baseurl` is empty (site at the root).
- **Where content lives:**
  - About page: `_pages/about.md`. Profile photo: `assets/img/prof_pic.jpg`.
  - News: `_news/`. Blog posts: `_posts/` (post URLs are `/:year/:title/`).
  - Publications: `_bibliography/papers.bib`. PDFs, slides and posters: `assets/pdf/`.
  - Other pages: `_pages/glotsuite.md` (GlotSuite tab), `_pages/service.md` (reviewing, organizing, supervision), `_pages/social.md` (hobbies + all profiles).
  - Social links: `_data/socials.yml`. Co-author links: `_data/coauthors.yml`.
  - Projects, teaching and books pages exist but are hidden from the menu until they have content.
- **Publication logos:** each bib entry has `preview = {<name>.png}` from `assets/img/publication_preview/`. The editable source is `publication-logos.excalidraw` in the same folder. The Glot marks come from the `glotlid-slides` repo (`logo/`).
- **Custom bibtex keys** (buttons added in `_layouts/bib.liquid`): `acl`, `acm`, `ieee`, `demo`, `oral`, `area_chair_award`, `best_student_paper`, `best_paper`, `pdf_v1`, `pdf_v2`. A new custom key must also be added to `filtered_bibtex_keywords` in `_config.yml`.
- **Local overrides of gem files** (kept on purpose; re-check them when bumping `al_folio_core`):
  - `_layouts/bib.liquid`: the custom publication buttons above.
  - `_includes/header.liquid`: the navbar shows only email, Scholar, GitHub, LinkedIn, X and Hugging Face.
  - `_sass/_themes.scss`: green theme color `#025c00` in light mode (cyan in dark mode).
  - `_includes/news.liquid`: adds the "see all the news here" line under the news on the about page.
  - `_layouts/about.liquid`: plain "news" / "latest posts" headings and a "see all the posts here" line.
- **Removed on purpose:** the CV feature (the `al_folio_cv` gem, the cv page and rendercv) and the repositories page. Don't add them back.
- **CI:** `deploy.yml` builds and publishes the site; the other workflows are link checks, CodeQL, the al-folio upgrade audit, weekly citation updates and a manual run-cleanup. The upstream template's own test, visual-regression, Prettier, Lighthouse, star-history, screenshot, release and CV workflows were removed on purpose.

## Personal License

Feel free to use template for your own purposes, but please respect copyright for all the personal images and contents.

## al-folio License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

Originally, [al-folio](https://github.com/alshedivat/al-folio/) was based on the [\*folio theme](https://github.com/bogoli/-folio) (published under the MIT license).
Since then, it got a full re-write of the styles and many additional cool features.
