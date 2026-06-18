# Contributing to the ERA Lab website

Lab members edit the site directly with Git. There are no build tools to install
— everything is plain text (Markdown + YAML) and images. When you push to `main`,
GitHub Pages rebuilds and publishes the site automatically (usually within a
minute or two).

> **Heads-up:** pushes go straight to the live site. Double-check your changes
> before pushing, and pull the latest first so you don't overwrite someone else.

## One-time setup

1. Ask the maintainer to add you as a **collaborator** with write access
   (repo → *Settings* → *Collaborators* → *Add people*). Accept the email invite.
2. Clone the repo:
   ```bash
   git clone https://github.com/era-research-lab/era-research-lab.github.io.git
   cd era-research-lab.github.io
   ```

## Add or edit content

Most updates are just editing a data file in [`_data/`](_data/) — each file has a
header comment explaining its fields:

| To update…            | Edit…                          |
|-----------------------|--------------------------------|
| People / your profile | `_data/people.yml`             |
| Projects (cards)      | `_data/projects.yml`           |
| Publications          | `_data/publications.yml`       |
| News                  | `_data/news.yml`               |
| Robots & platforms    | `_data/robots.yml`             |
| Fun gallery           | `_data/fun.yml`                |

Add any images to the matching folder under `assets/images/` and reference them
by filename. Always include descriptive `alt` text on images.

To add a **full project page**, see [`projects/README.md`](projects/README.md)
and the [`projects/TEMPLATE.md`](projects/TEMPLATE.md) template.

## Push your changes

```bash
git pull                      # always pull first
git add .
git commit -m "Add <your project / update>"
git push                      # publishes to the live site
```

Wait ~1–2 minutes, then refresh https://era-research-lab.github.io to see it live.
If the page doesn't update, check the repo's **Actions** tab for a failed build.

## Etiquette

- **Pull before you push** to avoid conflicts.
- Only edit your own profile and your own project pages unless coordinating.
- Keep commits small and write a clear commit message.
- Don't commit huge raw files — resize images to a reasonable web size first.
