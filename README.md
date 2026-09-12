# CV

My CV built using LaTeX.

## Structure

- `resume_cv.tex` - Main document file
- `awesome-cv.cls` - Custom document class for styling
- `fontawesome.sty` - Font Awesome icon package
- `cv-sections/` - Sections of the CV
  - `education.tex` - Education history
  - `experience.tex` - Work experience
  - `skills.tex` - Technical skills
  - `soft-skills.tex` - Soft skills
- `fonts/` - Bundled Roboto, Source Sans Pro and Font Awesome fonts
- `.github/workflows/build-cv.yml` - CI workflow that builds the PDF

## Building

The PDF is built by GitHub Actions. On every push that changes a `.tex`, `.cls` or `.sty` file, the fonts or the workflow itself, the pipeline:

1. Compiles `resume_cv.tex` with XeLaTeX in the [`texlive/texlive`](https://hub.docker.com/r/texlive/texlive) Docker image
2. Fails if the build errors or the CV is not exactly 2 pages, and flags overfull boxes as warnings
3. Commits the rebuilt `resume_cv.pdf` back to the branch if it changed, so pull after pushing

To build locally instead, you need a TeX distribution with XeLaTeX (e.g. TeX Live):

```bash
xelatex -interaction=nonstopmode resume_cv.tex
```

Or use your preferred LaTeX editor/IDE with XeLaTeX as the engine.

## Preview

You can view the latest version of my CV [here](resume_cv.pdf).
