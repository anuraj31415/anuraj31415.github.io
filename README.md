# site

Source for Anu's personal site, published at <https://anuraj31415.github.io>.

It is a plain static site: `index.html`, `style.css` and `404.html` (the 404 page
is served by GitHub Pages for unknown paths). No JavaScript, no tracking and no
external resources: system fonts only. Green and red are the only accent colours,
and the 404 page uses the diff styling. `.nojekyll` tells GitHub Pages to serve
the files as-is without running Jekyll.

## Deployment

Every push to `main` triggers the GitHub Actions workflow in
`.github/workflows/pages.yml`, which uploads the repository as a Pages artifact
and deploys it. The workflow can also be started manually from the Actions tab
(`workflow_dispatch`).

In the repository settings, Pages must have its source set to
**GitHub Actions**.

## Local preview

```sh
python3 -m http.server
```

Then open <http://localhost:8000/>.

## Checks

```sh
grep -rEi "linked[i]n|anuraj3151[5]|<script|@import|url\(http|<img" index.html style.css 404.html  # no output
grep -oE "(href|src)=\"https?://[^\"]+" index.html | sort -u   # repos, GitHub, X only
wc -c index.html style.css 404.html                            # under 20 kB total
```

Palette contrast was checked with the WCAG formula (body, muted, add and del
text against the background in light and dark, hero lines against their tints).
