# Project Pages

Each file in this folder is one project page (for example, `pfs.md`). New pages
are created from [`TEMPLATE.md`](TEMPLATE.md).

## For lab members — make your project page

Lab members commit directly with Git (see [`../CONTRIBUTING.md`](../CONTRIBUTING.md)
for one-time setup and the push commands).

1. **Copy the template.** Duplicate `TEMPLATE.md` and rename it to your project
   slug, e.g. `oyster-mapping.md` (lowercase, dashes, no spaces).
2. **Fill it in.** Edit the front matter (title, authors, links, …) and write the
   body in Markdown. The template comments explain every field. Delete anything
   you don't need.
3. **Add your images.** Put them in `../assets/images/projects/` and reference
   them by filename. Include a short, descriptive `alt` text on every image.
4. **Go live.** Delete the `published: false` line in the front matter.
5. **Add your card.** Add a short entry to [`../_data/projects.yml`](../_data/projects.yml)
   so your project appears on the **Research** page. Point its `page:` field at
   your `permalink` (e.g. `/projects/oyster-mapping/`). Set `featured: true` to
   also show it on the Home page.
6. **Commit & push.** `git pull`, then commit your `.md`, images, and the
   `projects.yml` change, and `git push`. The site rebuilds automatically.

Want a finished example? Look at [`pfs.md`](pfs.md) — it was built from the
template.

> Not comfortable with Git? You can instead send your `.md` file **and** images
> to the maintainer and they'll plug it in (steps below).

## For the maintainer — plug it in

1. Drop the member's `.md` file into this `projects/` folder.
2. Copy their images into `../assets/images/projects/`.
3. Confirm the front matter: `layout: project`, a unique `permalink`
   (`/projects/<slug>/`), and that `published: false` is **removed**.
4. Add a card to [`../_data/projects.yml`](../_data/projects.yml) so the project
   shows up on the **Research** page (and Home, if you set `featured: true`).
   Point its `page:` field at the new `permalink`.
5. (Optional) Add the paper to [`../_data/publications.yml`](../_data/publications.yml)
   and/or a line to [`../_data/news.yml`](../_data/news.yml).
6. Commit and push — GitHub Pages rebuilds automatically.

No build tools are required for steps 1–5; everything is plain text + images.
