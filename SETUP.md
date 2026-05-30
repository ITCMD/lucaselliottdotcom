# Site setup & workflow

This Obsidian vault **is** the Hugo site for lucaselliott.com.

## Daily workflow
1. Edit your bio in `content/_index.md`, or add a project in `content/projects/`.
2. Commit + push with the Obsidian **Git** plugin (or a Buttons-plugin button).
3. Cloudflare Pages auto-builds and publishes within ~1 minute.

## Preview locally
```powershell
hugo server
```
Then open http://localhost:1313 . It live-reloads as you edit.

## Adding a project
Create `content/projects/my-thing.md`:
```markdown
---
title: "My Thing"
weight: 1            # lower = higher in the list
link: "https://my-thing.com"
image: ""            # blank = auto-fetch the site's preview image at build time
---
A one-to-three sentence blurb. This body text is the blurb.
```
- `image: "covers/foo.jpg"` → put the file in `assets/covers/foo.jpg`.
- `image: "https://..."` → use a remote image directly.
- `image: ""` with a `link` → Hugo scrapes the linked site's og:image when it builds.

## Your stuff to fill in
- `static/images/photo.svg` → replace with your real `photo.jpg` (then set `photo` in `hugo.toml`).
- `hugo.toml` → `name`, `tagline`, `description`, `resume` link, and `[[params.social]]` links.
- Delete the two `example-*.md` files in `content/projects/` once you've added real ones.

## Cloudflare Pages build settings
- Framework preset: **Hugo**
- Build command: `hugo --gc --minify`
- Build output directory: `public`
- Environment variable: `HUGO_VERSION` = `0.161.1`
