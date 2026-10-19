# Maintaining the ARMOR Lab website

The lab pages use `_layouts/armor.html` and `assets/css/armor.css`. Existing academic pages keep their original layouts and share the new main navigation.

- Navigation: `_data/navigation.yml`. Publications links directly to the existing Google Scholar profile.
- Research summaries and images: `_data/research.yml`; detailed descriptions: `_pages/research.md`.
- People: `_data/people.yml`. Add entries with `name`, `role`, and optional `url` to each group's `members` list. Empty groups display their placeholder message.
- Projects: `_data/projects.yml`. The first three also appear on the homepage.
- Facilities: `_data/facilities.yml`. Supply a site-relative `photo` path and descriptive `alt` text to replace each photo placeholder. Confirm equipment details before adding specifications.
- Homepage, recruitment, and contact text: `_pages/about.md`, `_pages/join-us.md`, and `_pages/contact.md`.

Use `relative_url` for internal links and images so the existing GitHub Pages base path is respected. Keep the existing logo and PI photograph in `images/`. Talks and Teaching remain at `/talks/` and `/teaching/` without main navigation entries.

## Local development

With Ruby and the Gemfile dependencies installed, run from the repository root:

```sh
bundle exec jekyll build
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

In the prepared cloud environment, first activate its local Ruby:

```sh
export PATH=/workspace/.cloud-tools/ruby/bin:$PATH
export BUNDLE_USER_HOME=/workspace/.cloud-tools/bundle-home
```

The development server serves the site under the configured `/Ben-Mingyu-Kim.github.io/` base path. Restart it after changing `_config.yml`. Check the seven lab pages at desktop and mobile widths, follow navigation and research anchors, and confirm images load. Generated output and local previews are ignored; never edit `_site/` as source.
