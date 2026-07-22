# Pushing this site to GitHub

The repo already exists and is empty:
`https://github.com/RPGroup-Monash/RPGroup-Monash.github.io`.
This folder is the full contents, ready to become its `main` branch.

I (Aru, in the sandbox) can't authenticate to GitHub, so run these on your Mac —
the same HTTPS path you used for `prabhakarranganathan/C2D2-Model`.

## 1. First push

```bash
cd "/Users/prabhakar/Documents/Claude/Projects/MMA2003 Thermofluids/RPGroup-Monash.github.io"

git init
git branch -M main
git add .
git commit -m "Seed group site: The Art of Solving Thermodynamics Problems"
git remote add origin https://github.com/RPGroup-Monash/RPGroup-Monash.github.io.git
git push -u origin main
```

If it asks for a password, use a **Personal Access Token** (classic, `repo`
scope), not your account password. macOS will remember it in the Keychain after
the first time.

> Prefer not to keep the repo nested inside the MMA2003 project folder? Move it
> anywhere first (e.g. `~/code/RPGroup-Monash.github.io`) and run the same
> commands there. The folder is self-contained.

## 2. Turn on Pages (once)

On GitHub: **Settings → Pages → Build and deployment → Deploy from a branch →
`main` / `/ (root)` → Save**. For a `<org>.github.io` repo this is often already
on after the first push; just confirm.

Give it a minute, then check:

- Group site — https://rpgroup-monash.github.io/
- **Teaching resource (the citable link)** — https://rpgroup-monash.github.io/teaching/art-of-solving/
- Method PDF — https://rpgroup-monash.github.io/teaching/art-of-solving/method.pdf

## 3. Later edits

```bash
git add -A && git commit -m "…" && git push
```

Pages redeploys automatically on each push to `main`.

---

### What's already wired to this URL

The Week 1 and Week 2 instructor solutions cite
`https://rpgroup-monash.github.io/teaching/art-of-solving/` on first mention of
the method. The link goes live the moment Pages finishes its first build; nothing
in the solutions needs changing afterwards.
