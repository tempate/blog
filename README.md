# blog

Personal blog, published with GitHub Pages as a project site of
[tempate.github.io](https://github.com/tempate/tempate.github.io), which puts it at
<https://tempate.github.io/blog/> (hence `baseurl: /blog` in `_config.yml`).

The site is a standalone Jekyll build. It carries its own copy of the layouts, stylesheet,
fonts and photo, so changes to the main site do not propagate here automatically.

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
