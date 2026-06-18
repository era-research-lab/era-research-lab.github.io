# ERA Lab Website

Website for the **Embodied Robotics and Autonomy (ERA) Lab** at the University of
South Florida, led by Prof. Xiaomin Lin. Built with **Jekyll** and deployed on
**GitHub Pages**.

Live site: <https://era-research-lab.github.io>

## How it's organized

```
_config.yml            Site-wide settings (title, PI, links, etc.)
index.html             Home page
people.html            People page          (data: _data/people.yml)
robots.html            Robots & platforms   (data: _data/robots.yml)
research.html          Research themes + projects (data: _data/research_themes.yml, _data/projects.yml)
publications.html      Publications         (data: _data/publications.yml)
news.html              News                 (data: _data/news.yml)
fun.html               Lab culture gallery  (data: _data/fun.yml)
opportunities.html     Opportunities & contact
projects/pfs.md        PFS project page     (layout: project)

_layouts/              default.html, page.html, project.html
_includes/             head, nav, footer, person-card
_data/                 YAML content (edit these to update the site)
assets/
  css/main.css         All styles (design tokens at the top)
  js/main.js           Mobile nav toggle
  images/people/       Headshots
  images/projects/     Project / publication thumbnails
  images/robots/       Robot photos
  images/news/         News images
  images/fun/          Gallery photos
```

## Updating content (no code needed)

Almost everything is data-driven. To update the site, edit the YAML files in
`_data/` — each file has a header comment explaining its fields.

- **Add a person:** edit `_data/people.yml`. Drop the headshot in
  `assets/images/people/` and reference its filename. Use `placeholder.png` if you
  don't have a photo yet.
- **Add a project:** edit `_data/projects.yml`. For a full project page, create
  `projects/<slug>.md` with `layout: project` (use `projects/pfs.md` as a template).
- **Add a publication / news item / robot / photo:** edit the matching `_data/*.yml`.

Items marked `# TODO` need real information filled in.

## Local preview

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

GitHub Pages builds the site automatically on every push to the default branch.
The site uses only GitHub Pages–supported features (no custom plugins).
