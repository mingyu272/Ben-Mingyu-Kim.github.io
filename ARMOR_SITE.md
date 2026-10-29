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

## News and event photos

Edit `_data/news.yml`. The News page sorts entries newest first; the homepage shows at most three. Use the filename's date precision: `YYYY-MM-DD` when a day is known, or `YYYY-MM` for a month-only date, and set the corresponding `date_label`. Never infer an event date from a file modification timestamp. Items sharing a month without known days have no asserted day-level chronology.

For event photos, add a site-relative `image` path, meaningful `alt` text, and a concise `caption`. Keep original aspect ratios. Archive-provided descriptions are reference material; confirm they support the caption before publishing.

Uploaded event photos are stored in `images/news/` with month-prefixed descriptive names. `_data/media_sources.yml` records their original filenames and source date precision. Published copies are EXIF-oriented, resized to fit within 1600 × 1600 pixels, and encoded as optimized JPEGs without embedded location metadata; original uploads remain outside the checkout. No photo is cropped. The homepage displays at most three news items with bounded image height. Facility photographs retain their full aspect ratio.

## Video and field media

`_includes/armor-video.html` renders responsive MP4 video with native controls, `playsinline`, `preload="none"`, a poster, an accessible label, and a download fallback. It never autoplays. Facility video paths and captions are configured in `_data/facilities.yml`. The June 2026 drone-training MOV was converted to H.264/AAC with HDR-to-SDR BT.709 tone mapping and `faststart`; its portrait orientation is preserved.

The homepage features the **unmanned-boat field-testing video**, supplied separately after `b.zip` and `c.zip`. It uses the same controlled video component and poster as the first Facilities category. Keep the homepage to one field-testing media feature; the drone-training video belongs only in the UAV section. Undated boat photos are used without dates. The undated ACC presentation photo is grouped as an additional event photo and explicitly captioned as undated. Additional event images are shown in expandable galleries on News, not on the homepage.

The boat MOV filename has no date, so its published filename, player caption, and provenance do not invent one. Both videos preserve portrait framing and use H.264/AAC, standard BT.709 color, and MP4 faststart for web playback. Original field-testing photographs remain available on Facilities.

Both the boat Facilities player and homepage feature use the repository-hosted MP4 directly, with no Google Drive embed or sign-in requirement. The Facilities video appears immediately after its heading and description; supporting boat photographs are expandable below it. Every player includes a visible “Open or download video” link for browsers or preview proxies that cannot stream the embedded player.

## Student profiles

Graduate, undergraduate, and alumni profiles share `_includes/armor-member.html`. Edit their entries in `_data/people.yml`: `name`, `role`, `department`, `institution`, `photo`, `photo_alt`, `education`, and `research`. Optional `experience`, `fun_fact`, and `motto` fields render only when supplied; `motto_attribution` supplies the quotation credit. Education records use `degree`, `institution`, and optional `years` or `status`. Store student portraits in `images/people/` and set a site-relative path. Student portraits use matching 160 × 160 pixel circular frames on desktop and mobile. Optional `photo_position` and `photo_zoom` fields center each face using CSS without modifying the original image files. Missing portraits show a labeled placeholder rather than a broken image.

News entries may include a `links` list with `label` and `url` fields for papers, conference sites, and related resources. These links appear on both News and the homepage news preview. For announcements without a supplied event date, use the announcement month and never invent an exact acceptance day.

## Lab Life gallery

The dedicated Lab Life page at `/lab-life/` sits between News and People in the main navigation and is maintained in `_data/gallery.yml`. News links to it; the photo is displayed only on Lab Life. Each entry has `id`, `title`, `image`, `alt`, and `caption`; `width`, `height`, `date`, and `date_label` are optional. Store photos in `images/gallery/` and preserve their aspect ratio. Clicking an image opens the full photo. Use a supplied event date or original capture metadata and record its provenance; do not infer an event date from upload time. The Olive Garden photo’s original DateTimeOriginal metadata records October 29, 2026; the page displays October 2026, as requested.

Award announcements can include an `awards` list with `student`, `classification`, `project`, and `funding`. News shows these details; the homepage keeps the summary and links to the complete announcement. Public news must omit student identification numbers. Dates use the announcement month unless an event date is supplied. Within a month, place newer announcements after earlier ones in the data file because the template reverses the stable date sort.
