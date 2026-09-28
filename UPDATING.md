# Updating the site

You don't need to touch any of this yourself. Ask Claude, e.g.:

- "Add a new article to my site: [title], [citation], SSRN link [url]. The PDF is attached."
- "Move 'Speakerless Government Speech' from works in progress to published: [citation]."
- "Post the Fall 2026 Civil Procedure final exam." (attach the PDF)
- "Add this op-ed to Writing & Media: [title], [outlet], [date], [url]."
- "Add a coursebook: [title], [H2O link], [one-line description]."

Every change is saved as a checkpoint in GitHub, so any change can be undone ("revert the last change").

## Where things live

| What | File |
|---|---|
| Name, title, email, profile links, footer credit | `hugo.yaml` |
| Articles and works in progress | `data/scholarship.yaml` |
| Commentary, talks, podcasts, press | `data/writing.yaml` |
| Courses, syllabi, exams, practice assessments | `data/teaching.yaml` (PDFs in `static/files/teaching/`) |
| Coursebooks | `data/coursebooks.yaml` |
| Research areas (homepage sidebar) | `data/research_areas.yaml` |
| Bio text | `content/bio.md` |
| Headshot | `static/images/headshot.jpg` |

## Editing on GitHub directly (optional)

Open a file on github.com, click the pencil icon, edit, and click "Commit changes." The site rebuilds itself within a couple of minutes. The YAML files are indentation-sensitive: copy an existing entry and change its text rather than typing one from scratch.

## Publishing

Every push to the `main` branch rebuilds and republishes the site through GitHub Actions (`.github/workflows/deploy.yml`). If the site doesn't update, open the repository's **Actions** tab; a red X means the build failed, and the error message there is what to paste to Claude.

## Search engines

The site is set to stay out of search results: every page tells search engines not to list it (`noindex`), `robots.txt` keeps crawlers away from the PDFs, and known AI crawlers are blocked. Anyone with the link can still open it. To let search engines list the site, set `search_hidden: false` in `hugo.yaml`.

## Keep in mind

- Everything in this repository is public, including PDFs that aren't linked from any page. Don't add files you wouldn't post.
- Keep file and page names stable once published; people link to them.
