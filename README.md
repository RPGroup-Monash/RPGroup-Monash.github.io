# RPGroup-Monash.github.io

The RPGroup (Monash University) website, served by GitHub Pages at
**https://rpgroup-monash.github.io/**.

## Layout

```
/
  index.html                     group landing page (placeholder — replace when ready)
  .nojekyll                      serve files verbatim, no Jekyll build
  teaching/
    art-of-solving/              "The Art of Solving Thermodynamics Problems"
      index.html                 the resource page
      method.pdf                 written companion — RP's method (4 pp)
      method.tex                 LaTeX source for method.pdf
      media/                     01-why_video.mp4, 02-how-to-plan_video.mp4
      slides/                    01-why_slides.pdf, 02-how-to-plan_slides.pdf
      transcripts/               01-why_transcript.pdf, 02-how-to-plan_transcript.pdf
```

## Live URLs

- Group site: https://rpgroup-monash.github.io/
- Teaching resource (cite this): **https://rpgroup-monash.github.io/teaching/art-of-solving/**
- Method PDF direct: https://rpgroup-monash.github.io/teaching/art-of-solving/method.pdf

## Publishing

This is a **user/organisation Pages site**, so the `main` branch of this repo is served
directly at the root domain. See `PUSH.md` for the first-push commands. After pushing,
enable Pages once: **Settings → Pages → Build and deployment → Deploy from a branch →
`main` / `/ (root)`**.

## Rebuilding the method PDF (only if you edit the source)

```bash
cd teaching/art-of-solving
pdflatex method.tex && pdflatex method.tex
```

## Notes

- The videos are committed directly (≈6 MB + ≈14 MB, within GitHub's 100 MB/file limit).
- `index.html` at the root is a light placeholder; replace it with a proper group homepage
  whenever you like — the teaching resource lives at its own stable path and is unaffected.
