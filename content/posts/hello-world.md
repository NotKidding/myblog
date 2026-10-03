---
title: "Hello World!"
date: 2026-09-15T06:53:22Z
draft: false
tags: ["meta", "Writeup", "Security Blog", "OffSec"]
summary: "First post — why this blog exists and how it's built."
showToc: true
---

## Why this exists

This is a companion to my [portfolio site](https://nandakumar.online) —
a place for longer-form notes on offensive security: lab writeups, tool
notes, and things I learn the hard way while working toward a career in
red teaming.

## How it's built

A quick rundown, mostly for my own future reference:

- **Generator:** [Hugo](https://gohugo.io), static, fast, no server to secure.
- **Theme:** [PaperMod](https://github.com/adityatelange/hugo-PaperMod),
  reskinned with a `custom.css` override to match the palette and
  typography of my portfolio (Space Grotesk + JetBrains Mono, dark navy
  and cyan).
- **Hosting:** GitHub Pages, deployed automatically via GitHub Actions
  on every push to `main` — no manual `gh-pages` branch pushes.
- **Domain:** `blog.nandakumar.online`, a subdomain of my main domain,
  pointed here with a single DNS `CNAME` record.
- **Comments:** [giscus](https://giscus.app), backed by GitHub
  Discussions on this repo — no third-party comment service holding
  reader data.
- **Analytics:** a self-hosted, cookie-free option (GoatCounter or
  Plausible CE) — no Google Analytics.

## Workflow

Posts are plain Markdown with YAML frontmatter, written in Obsidian and
synced into this repo's `content/posts/` folder. `hugo new posts/my-post.md`
scaffolds a new one from the archetype in `archetypes/posts.md`.

More writeups soon.
