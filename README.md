# blog

Personal blog, published with GitHub Pages as a project site of
[tempate.github.io](https://github.com/tempate/tempate.github.io), which puts it at
<https://tempate.github.io/blog/> (hence `baseurl: /blog` in `_config.yml`).

The site is a standalone Jekyll build that loads the main site's published stylesheet
directly, followed by `assets/css/style.css` for the blog's centered layout and post
formatting. Shared fonts, colors, typography and interaction styles update automatically
when the main site is deployed, subject to normal browser caching; no blog rebuild is
needed. Keep shared design changes in the main site rather than copying them here.

`main_site_url` in `_config.yml` sets the shared stylesheet and font origin. It stays
pointed at the published site during local previews, which therefore need an internet
connection for the shared styles and fonts. The blog maintains its own layouts and images.

Posts go in `_posts/`, named `YYYY-MM-DD-slug.md`, with `title` and `date` front matter and
an optional `summary` shown on the index. They are served at `/blog/:title/`.

The blog is deliberately unlisted. Nothing on the main site links to it, no sitemap is
generated, and every page is `noindex, nofollow`. That only keeps it out of search results —
this repository is public, so the Markdown is readable on GitHub either way.

## Local preview

```sh
bundle install
bundle exec jekyll serve
```

## Licence

[MIT](LICENSE).
