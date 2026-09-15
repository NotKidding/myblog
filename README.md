# myblog

Source for `blog.nandakumar.online` — built with [Hugo](https://gohugo.io)
+ [PaperMod](https://github.com/adityatelange/hugo-PaperMod), reskinned to
match [nandakumar.online](https://nandakumar.online).

## Local dev

```bash
git clone --recurse-submodules <this-repo-url>
cd myblog
hugo server -D   # -D includes drafts
```

Requires Hugo **extended** v0.166.0+ (matches `.github/workflows/deploy.yml`).
If your package manager's Hugo is older than that, PaperMod will fail to
build — grab a current binary from
https://github.com/gohugoio/hugo/releases instead.

## New post

```bash
hugo new posts/my-post-slug.md
```

Uses the frontmatter template in `archetypes/posts.md`. Defaults to
`draft: true` — flip to `false` (or run `hugo --buildDrafts` locally to
preview) before it'll appear on the live build.

## Deploy

Push to `main` — `.github/workflows/deploy.yml` builds with Hugo and
publishes to GitHub Pages automatically. No manual `gh-pages` branch.

## Custom domain

- `static/CNAME` contains `blog.nandakumar.online` (copied into every
  build's output root).
- DNS: a `CNAME` record for `blog` → `notkidding.github.io` at the
  registrar for `nandakumar.online`.
- GitHub: Settings → Pages → Custom domain → `blog.nandakumar.online`,
  then enable "Enforce HTTPS" once the cert issues.

## Still to wire up

- **giscus comments**: `params.comments: true` is set, but the giscus
  partial/script (repo, category, mapping) still needs the IDs from
  https://giscus.app once GitHub Discussions is enabled on this repo.
- **Analytics**: GoatCounter or Plausible CE snippet not yet added —
  needs an account/self-hosted instance URL first.

## Theme override

All visual customization lives in `assets/css/extended/custom.css`,
loaded after PaperMod's own stylesheet — the theme itself (in
`themes/PaperMod/`, a git submodule) is never edited directly, so it can
be updated safely with `git submodule update --remote`.
