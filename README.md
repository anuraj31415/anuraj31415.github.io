# site

Source for Anu's personal site, published at <https://anuraj31415.github.io>.

It is a plain static site: `index.html` and `style.css`, with no JavaScript,
no tracking and no external resources. `.nojekyll` tells GitHub Pages to serve
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
