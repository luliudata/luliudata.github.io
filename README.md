# luliudata.github.io

Source for [luliudata.github.io](https://luliudata.github.io) — Lu Liu's
personal site and blog.

Built with [Jekyll](https://jekyllrb.com/) on the
[contrast](https://github.com/niklasbuschmann/contrast) theme by
Niklas Buschmann, with a custom palette, light/dark toggle, and
English / 中文 bilingual content.

## Local development

```bash
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000.

## Content

- Posts live in `_posts/` (English) and `_posts/zh/` (中文).
- Static pages: `index.md`, `blog.md`, `projects.md`, with `/zh/` mirrors
  for the Chinese versions.
- Site config: `_config.yml`. UI strings used by templates live in
  `_data/i18n.yml`.

## License

Site content © Lu Liu. The underlying theme is released under the
[Unlicense](UNLICENSE.txt) by its original author.
