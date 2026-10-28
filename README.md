# Daofu Zhang — personal website

A static, single-page academic homepage. Plain HTML/CSS with a few lines of JS (dark-mode toggle, BibTeX expand/copy). No build step.

```
index.html                 the page
assets/css/style.css       styles (light + dark theme tokens at the top)
assets/img/profile.svg     placeholder avatar (initials)
assets/img/favicon.svg     browser-tab icon
cv/Daofu_Zhang_Research_CV.pdf    CV linked from the site
cv/Daofu_Zhang_Research_CV.html   CV source (re-export the PDF from this)
.nojekyll                  tells GitHub Pages to serve files as-is
```

## Preview locally

```bash
python3 -m http.server 8765
```

Run it from this folder, then open http://localhost:8765.

## Things to fill in

- **Photo**: save a square photo as `assets/img/profile.jpg`, then in `index.html` change the avatar `src` from `assets/img/profile.svg` to `assets/img/profile.jpg`.
- **Links**: Google Scholar / LinkedIn lines are commented out in `index.html` (search for `Add when available`). Uncomment and replace the placeholders.
- **News**: add new items at the top of the `<ul class="news">` list.
- **Publications**: copy an existing `<li class="pub">` block. Status tag classes: `ok` (published), `wait` (under review), `info` (submitted).

## Re-export the CV PDF

After editing `cv/Daofu_Zhang_Research_CV.html`, run from this folder:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --no-pdf-header-footer --print-to-pdf="$PWD/cv/Daofu_Zhang_Research_CV.pdf" "file://$PWD/cv/Daofu_Zhang_Research_CV.html"
```

## Deploy with GitHub Pages

1. Create a public repository named `<your-github-username>.github.io`.
2. Push the contents of this folder to its `main` branch.
3. In the repository, go to Settings → Pages and set the source to `main` / root.
4. The site goes live at `https://<your-github-username>.github.io` within a minute or two.
