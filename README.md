# annakalygina.github.io

Minimalist personal site — plain HTML + CSS, no build step.

## Structure
- `index.html` — about / landing
- `research.html`
- `essays.html`
- `cv.html`
- `assets/css/style.css` — all styles
- `assets/img/` — hand-drawn PNG section headers
- `.nojekyll` — disables GitHub's Jekyll processing

## Local preview
```
python3 -m http.server 8000
```
Then open http://localhost:8000.

## Editing
Search for `TODO` to find content placeholders. The CSS class `.todo` highlights them yellow on the live site so you can see what's still unfilled.

To add a hand-drawn section header, drop a PNG into `assets/img/` and uncomment the `<img>` tag inside the matching `.section-heading` block.

## Enabling comments on essays (giscus)
Each essay page has a placeholder `comments` section. To turn on real comments:
1. On GitHub, go to **Settings → General → Features** and enable **Discussions** for this repo.
2. Install the giscus GitHub App: <https://github.com/apps/giscus>.
3. Create a Discussions category called e.g. "Essay comments" (use the **Announcements** type so only maintainers can start threads).
4. Visit <https://giscus.app>, paste the repo `AnnaKalygina/annakalygina.github.io`, pick the category, set Mapping = `pathname`, theme = `light`.
5. Copy the generated `<script>` block. Inside each `essays/*.html`, uncomment the `<script>` inside `<section class="comments">` and paste in the `data-repo-id` and `data-category-id` values from giscus.app.
6. (Optional) also replace the "comments will appear here once configured" paragraph with empty content — giscus injects its own iframe in place of the script tag.

Comments are stored as GitHub Discussions, so you get moderation, threading, reactions, and markdown for free, with no third-party tracking.
