# redrocket.fysh.site

Static download page for [Red Rocket](https://github.com/Fysh-ball/RedRocket).

Served by Cloudflare Pages. Every file here is the deploy output: there is no
build step, Pages publishes the repo root as-is.

## Editing

The page is a single self-contained `index.html`: styles and the one small script
are inline, and the CSP on the host blocks external fonts and CDNs, so keep it
that way.

## The og card

`og-card.png` is generated from `og-card.svg` at 1200x630. If you replace it, bump
the `?v=` date on both `og:image` and `twitter:image` in `index.html`. Cloudflare
serves it with max-age=14400 and there is no purge tooling, so an unversioned
replacement stays stale at the edge for up to four hours, and the social platforms
cache their own copy on top of that.

## Facts that must stay true

The download button, the size, and the SHA-256 on the page all describe the real
release asset. If a new version ships, all three change together, and the hash is
the one people check with `sha256sum`.

AGPL-3.0, same as the app.
