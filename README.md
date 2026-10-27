# ferreram.github.io

Personal website of Maxime Ferrera, built with [al-folio](https://github.com/alshedivat/al-folio) (Jekyll) and deployed to GitHub Pages by GitHub Actions.

## Where things live

| To change                       | Edit                                                                                     |
| ------------------------------- | ---------------------------------------------------------------------------------------- |
| Bio, photo, home page           | `_pages/about.md`, `assets/img/prof_pic.jpg`                                             |
| Publications                    | `_bibliography/papers.bib` (add `selected = {true}` to show a paper on the home page)    |
| News items                      | one file per item in `_news/`                                                            |
| Technical notes (blog)          | one file per post in `_posts/` named `YYYY-MM-DD-title.md`                               |
| PhD / internship openings       | `_openings/` (hidden for now: set `output: true` for `openings` in `_config.yml` and remove `published: false` from `_pages/openings.md`) |
| Research projects               | `_projects/` (hidden for now, same switch as openings)                                    |
| Teaching                        | `_teachings/` (hidden for now, same switch as openings)                                   |
| Social links                    | `_data/socials.yml`                                                                      |
| Site-wide settings              | `_config.yml`                                                                            |
| Files linked from pages (PDFs)  | `files/`                                                                                 |

## Local preview

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

Or with Docker: `docker compose up`.

## Deployment

Every push to `master` runs `.github/workflows/deploy.yml`, which builds the site and pushes it to the `gh-pages` branch. In the repository settings, GitHub Pages must serve from the `gh-pages` branch (Settings → Pages → Build and deployment → Deploy from a branch → `gh-pages` / root).
