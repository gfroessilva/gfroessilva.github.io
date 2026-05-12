# gfroessilva.github.io

This [site](https://gfroessilva.github.io) is now powered by [Quarto](https://quarto.org/).

## Local development

Render the website with:

```powershell
quarto render
```

The Quarto source files live in the repository root and render to the same root-level HTML files used by the GitHub Pages site.

## Automated resume sync from Overleaf

The repository includes a GitHub Actions workflow at `.github/workflows/sync-resume.yml` that pulls the resume source from Overleaf, compiles it with LaTeX, and updates `Guilherme_s_CV.pdf`.

Configure these repository **Actions secrets** before running it:

- `OVERLEAF_GIT_URL`
- `OVERLEAF_GIT_USERNAME`
- `OVERLEAF_GIT_TOKEN`

The workflow first tries to infer the main LaTeX file by looking for the root `.tex` file that contains `\documentclass`. If your Overleaf project still has multiple possible entrypoints, add this repository **Actions variable**:

- `OVERLEAF_MAIN_TEX` (example: `resume.tex`)

After that, you can run the workflow manually from the **Actions** tab or let the schedule keep the PDF in sync automatically.
