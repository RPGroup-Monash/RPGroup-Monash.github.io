# How to update this site

Live at https://computesoftmatter.org, served by GitHub Pages from
`RPGroup-Monash/RPGroup-Monash.github.io`, branch `main`, with DNS on Cloudflare.

## The one rule

This folder is the only working copy. There used to be a second clone under
`MMA2003 Thermofluids/`, and a force-push from it wiped the CReSI home page and the
S4F archive in July 2026. That clone was deleted on 5 September 2026. If you ever
need another copy, clone it fresh and delete it when you are done rather than
keeping two around.

Never use `git push --force` on this repo.

## What is here

- `index.html` — the CReSI Lab home page, self-contained, inline CSS, no build step.
- `meetings/S4F-2025/` — archived static capture of the S4F 2025 workshop site.
- `teaching/art-of-solving/` — The Art of Solving Thermodynamics Problems, slides,
  transcripts and videos.
- `teaching/thermocalc/` — the ThermoCalc perfect-ideal-gas calculator for MMA2003.
- `CNAME` — holds the custom domain. Do not delete it; Pages needs it on every commit.
- `.nojekyll` — stops GitHub running Jekyll over the files.

## Making a change

```bash
cd ~/Documents/Claude/Projects/Ops/computesoftmatter-site
git pull --ff-only
# edit files
git add -A
git commit -m "Describe the change"
git push origin main
```

Pages rebuilds within a minute or so. Hard-refresh the browser, Cmd-Shift-R, or you
will keep seeing the cached page.

## If the push is rejected

`Permission denied ... 403` means the org permission, not your machine. Create a
fine-grained token at github.com/settings/personal-access-tokens with resource owner
RPGroup-Monash, repository RPGroup-Monash.github.io, Contents set to read and write,
then:

```bash
git push https://YOUR_TOKEN@github.com/RPGroup-Monash/RPGroup-Monash.github.io.git main
```

Revoke the token afterwards and clear that line from your shell history.

`Updates were rejected (fetch first)` means the remote has commits you do not. Run
`git pull --ff-only` and push again. If that refuses because the histories have
diverged, stop and work out why before doing anything else. Do not force.

## Checking what is live without waiting for DNS

```bash
curl -sI --resolve computesoftmatter.org:443:185.199.108.153 https://computesoftmatter.org/
```
