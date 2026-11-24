# Daniel891116.github.io

Personal academic website of Yao-Ting (Daniel) Huang — https://daniel891116.github.io

Built with Jekyll and the [al-folio](https://github.com/alshedivat/al-folio) theme. Pushing to `master` triggers `.github/workflows/deploy.yml`, which builds the site and publishes it to the `gh-pages` branch.

## Where things live

| Content | File |
| --- | --- |
| Home page (bio, research interests, current projects) | `_pages/about.md` |
| Publications | `_bibliography/papers.bib` (preview images in `assets/img/publication_preview/`) |
| News items on the home page | `_news/*.md` |
| Project pages | `_projects/*.md` |
| Web CV | `_data/cv.yml` (keep in sync with `assets/pdf/CV_Yao-Ting_Huang.pdf`) |
| Site-wide settings (name, description, links) | `_config.yml` |

## Local preview

```bash
docker compose up        # then open http://localhost:8080
# or, with Ruby installed:
bundle install && bundle exec jekyll serve
```
