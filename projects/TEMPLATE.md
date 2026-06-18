---
# =============================================================
# ERA LAB — PROJECT PAGE TEMPLATE
# -------------------------------------------------------------
# HOW TO USE (lab members):
#   1. Copy this file to projects/<your-project-slug>.md
#      e.g. projects/oyster-mapping.md   (use lowercase-with-dashes)
#   2. Fill in everything below. Delete the parts you don't need.
#   3. Put your images in  assets/images/projects/  and reference
#      them by filename (see the body section).
#   4. DELETE the line `published: false` at the bottom of this
#      front matter so the page goes live.
#   5. Add a card for your project to  _data/projects.yml  (point its
#      `page:` field at the permalink below) so it shows on Research.
#   6. Commit and push:  git pull && git add . && git commit && git push
#      The live site rebuilds automatically. See ../CONTRIBUTING.md.
#
# Need an example? Open projects/pfs.md — it's a finished page
# built from this exact template.
# =============================================================

layout: project          # <-- keep this. it gives you the project page styling.

# --- Page title (shows as the big heading) ---
title: "Your Project Title: A Short, Descriptive Subtitle"

# --- The page's web address. Keep the /projects/ prefix. ---
permalink: /projects/your-project-slug/

# --- Optional little pill shown above the title (venue, status, etc.) ---
# Delete this line if you don't have one.
badge: "Venue / Year"          # e.g. "CVPR 2026"  or  "Under Review"  or  "In Progress"

# --- One-sentence summary used for search engines / link previews ---
description: One or two sentences summarizing the project.

# --- Authors. Add a url to make a name clickable; omit url for plain text. ---
authors:
  - { name: "First Author",  url: "https://example.com" }
  - { name: "Second Author" }
  - { name: "Xiaomin Lin",   url: "https://xiaominlin.github.io/" }

# --- Affiliation line under the authors (free text). Delete if not needed. ---
affiliations: "ERA Lab, University of South Florida"

# --- Buttons at the top of the page. Delete any you don't have. ---
# icon = a Font Awesome or Academicons class. Common ones:
#   arXiv .......... "ai ai-arxiv"
#   PDF / Paper .... "fas fa-file-lines"
#   Code / GitHub .. "fab fa-github"
#   Video .......... "fab fa-youtube"
#   Dataset ........ "fas fa-database"
#   Project/Website  "fas fa-globe"
links:
  - { label: "Paper",   url: "https://arxiv.org/abs/XXXX.XXXXX", icon: "ai ai-arxiv" }
  - { label: "Code",    url: "https://github.com/your/repo",     icon: "fab fa-github" }
  - { label: "Video",   url: "https://youtu.be/XXXXXXXX",        icon: "fab fa-youtube" }
  - { label: "Dataset", url: "#",                                 icon: "fas fa-database" }

# Keep this while editing so the half-finished page is NOT published.
# DELETE this line when your page is ready to go live.
published: false
---

<!-- ============================================================
     BODY — everything below is your page content.
     Write in Markdown. You can paste HTML blocks (like the figure
     and video below) wherever you want them.
     ============================================================ -->


<!-- ---------- TEASER / HERO FIGURE (optional) ----------
     Put your main figure here. Replace the filename with your image
     in assets/images/projects/ . Always include descriptive alt text. -->
<figure>
  <img src="{{ '/assets/images/projects/your-teaser.png' | relative_url }}"
       alt="Describe your figure for screen readers">
  <figcaption>
    A caption describing the teaser figure / system overview.
  </figcaption>
</figure>


## Overview

Write a short, plain-language overview of the project: what problem it
addresses, the core idea, and why it matters. Two or three short paragraphs
is plenty.


## Approach

Explain your method. You can add figures anywhere like this:

<figure>
  <img src="{{ '/assets/images/projects/your-method.png' | relative_url }}"
       alt="Describe the method figure">
  <figcaption>Method overview.</figcaption>
</figure>

You can **bold** key terms, use bullet points:

- Key idea one
- Key idea two
- Key idea three

…and inline math-free explanations. Keep paragraphs short and readable.


## Video  <!-- optional — delete this whole section if you have no video -->

<div class="video-embed">
  <iframe src="https://www.youtube.com/embed/XXXXXXXX"
          allow="autoplay; encrypted-media" allowfullscreen title="Project video"></iframe>
</div>


## Results

Summarize results in text, with a figure or a simple table:

| Method        | Metric A | Metric B |
|---------------|:--------:|:--------:|
| Baseline      |   00.0   |   00.0   |
| **Ours**      | **00.0** | **00.0** |

<!-- Don't have results yet? Use a placeholder box so the section
     still looks intentional: -->
<!-- <div class="placeholder-box">Results coming soon</div> -->


## Acknowledgments  <!-- optional -->

Thank funders, collaborators, or compute providers here.


## BibTeX  <!-- optional — delete if there's nothing to cite yet -->

```bibtex
@article{yourkey2026,
  title   = {Your Project Title},
  author  = {First Author and Second Author and Xiaomin Lin},
  journal = {arXiv preprint arXiv:XXXX.XXXXX},
  year    = {2026}
}
```
