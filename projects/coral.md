---
layout: project

title: "CORAL: COntextual Reasoning And Local Planning in A Hierarchical VLM Framework for Underwater Monitoring"

permalink: /projects/coral/

badge: "Accepted to IROS 2026"

description: A hierarchical VLM framework that decouples high-level semantic reasoning from low-level reactive control for autonomous underwater oyster reef monitoring.

authors:
  - { name: "Zhenqi Wu",   url: "https://zhenqi72.github.io/Personal_website/" }
  - { name: "Yuanjie Lu" }
  - { name: "Xuesu Xiao" }
  - { name: "Xiaomin Lin", url: "https://xiaominlin.github.io/" }

affiliations: "University of South Florida & George Mason University"

links:
  - { label: "Paper", url: "https://arxiv.org/abs/2603.14786", icon: "ai ai-arxiv" }
  - { label: "Video", url: "https://youtu.be/a44yB6STV7Y",     icon: "fab fa-youtube" }
  - { label: "Code",  url: "#",                                 icon: "fab fa-github" }

---

<!-- Teaser: exported from the original overview.pdf at 300 DPI. -->
<figure>
  <img src="{{ '/assets/images/projects/coral-teaser.png' | relative_url }}"
       alt="CORAL system overview: hierarchical VLM planner over MDDP low-level controller for underwater reef monitoring">
  <figcaption>
    CORAL decouples high-level semantic reasoning (VLM planner) from low-level
    reactive control (MDDP), validated in simulation and on a BlueROV2 in a
    controlled pool.
  </figcaption>
</figure>

<!-- Grid styles for 5-up simulation environments and trajectories.
     Namespaced under .coral- so they don't collide with the site layout. -->
<style>
  .coral-grid-5 {
    display: grid; grid-template-columns: repeat(5, 1fr);
    gap: 0.75rem; margin: 1.5rem 0;
  }
  .coral-grid-5 figure { margin: 0; }
  .coral-grid-5 .coral-card {
    border: 1px solid #e0e0e0; border-radius: 6px; overflow: hidden;
    transition: border-color 0.2s, box-shadow 0.2s;
  }
  .coral-grid-5 .coral-card:hover {
    border-color: #aaa; box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  .coral-grid-5 .coral-card img {
    width: 100%; display: block;
    aspect-ratio: 4 / 3; object-fit: cover;
  }
  .coral-grid-5.coral-traj .coral-card img { aspect-ratio: 1 / 1; }
  .coral-grid-5 figcaption {
    padding: 0.4rem 0.5rem; font-family: 'DM Mono', monospace;
    font-size: 0.65rem; color: #666; text-align: center;
    border-top: 1px solid #efefef; letter-spacing: 0.06em; line-height: 1.4;
  }
  @media (max-width: 760px) {
    .coral-grid-5 { grid-template-columns: repeat(2, 1fr); }
  }
</style>



## Abstract

Oyster reefs are critical ecosystem species that sustain biodiversity, filter
water, and protect coastlines, yet 85% have been lost globally. Restoring these
ecosystems requires regular underwater monitoring to assess reef health, a task
that remains costly, hazardous, and limited when performed by human divers.
Autonomous underwater vehicles (AUVs) offer a promising alternative, but
existing AUVs rely on geometry-based navigation that cannot interpret scene
semantics. Recent vision-language models (VLMs) enable semantic reasoning for
intelligent exploration, but existing VLM-driven systems adopt an end-to-end
paradigm, introducing three key limitations: frequent inference delays, weak
dynamics awareness, and limited self-correction.

We propose **CORAL**, a framework that decouples high-level semantic reasoning
from low-level reactive control. The VLM provides high-level exploration
guidance by selecting waypoints, while a dynamics-based planner handles
low-level collision-free execution. A geometric verification module validates
waypoints and triggers replanning when needed. Compared with the previous
state-of-the-art, CORAL improves coverage by **14.28 percentage points**,
reduces collisions by **100%**, and requires **57% fewer VLM calls**.


## Method

CORAL separates the navigation stack into three tightly integrated layers: a
persistent occupancy map with centroid chain extraction, a VLM high-level
planner invoked only at meaningful decision points, and a dynamics-aware MDDP
low-level controller running continuously at 10 Hz.

- **Perception & Centroid Chain** — Depth and segmentation images are fused
  into a persistent 2D occupancy map. Cluster centroids are extracted and
  organized into an ordered chain with cross-frame exponential smoothing.
- **VLM High-Level Planner** — A smart trigger invokes the VLM only on goal
  arrival, stuck detection, or planner failure. A geometric verifier rejects
  backward or off-trend waypoints with structured corrective feedback.
- **MDDP Low-Level Controller** — Decremental Dynamics Planning augments MPPI
  with variable-fidelity dynamics — dense near the robot, progressively
  simplified farther along — enabling long-horizon planning at zero collisions.


## Simulation

We evaluate CORAL across five reef-topology environments of increasing
complexity. Each environment is shown below with its coverage result and a
playback of the full mission.

<div class="coral-grid-5">
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-L-shape.png' | relative_url }}" alt="L-Shape reef simulation environment"></div>
    <figcaption>L-Shape — 100%</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-S-shape.png' | relative_url }}" alt="S-Shape reef simulation environment"></div>
    <figcaption>S-Shape — 92.86%</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-O-shape.png' | relative_url }}" alt="O-Shape reef simulation environment"></div>
    <figcaption>O-Shape — 100%</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-K-shape.png' | relative_url }}" alt="K-Shape reef simulation environment"></div>
    <figcaption>K-Shape — 83.33%</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-E-shape.png' | relative_url }}" alt="E-Shape reef simulation environment"></div>
    <figcaption>E-Shape — 100%</figcaption>
  </figure>
</div>


### Simulation videos

- **L-Shape** — <https://www.youtube.com/watch?v=f_jGZbtpLJ8>
- **S-Shape** — <https://www.youtube.com/watch?v=-eZtqSa4JVw>
- **O-Shape** — <https://www.youtube.com/watch?v=QMioBT-mZ8w>
- **K-Shape** — <https://www.youtube.com/watch?v=gmfq7FswaL4>
- **E-Shape** — <https://www.youtube.com/watch?v=F-hgrJ9SHFg>

### Trajectories

Coverage trajectories across all five environments, comparing **DREAM**,
**CORAL w/o Low-Level**, and **CORAL (Full)**.

<div class="coral-grid-5 coral-traj">
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-L-shape-trajectory.png' | relative_url }}" alt="L-Shape coverage trajectory comparison"></div>
    <figcaption>L-Shape</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-S-shape-trajectory.png' | relative_url }}" alt="S-Shape coverage trajectory comparison"></div>
    <figcaption>S-Shape</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-O-shape-trajectory.png' | relative_url }}" alt="O-Shape coverage trajectory comparison"></div>
    <figcaption>O-Shape</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-K-shape-trajectory.png' | relative_url }}" alt="K-Shape coverage trajectory comparison"></div>
    <figcaption>K-Shape</figcaption>
  </figure>
  <figure>
    <div class="coral-card"><img src="{{ '/assets/images/projects/coral-E-shape-trajectory.png' | relative_url }}" alt="E-Shape coverage trajectory comparison"></div>
    <figcaption>E-Shape</figcaption>
  </figure>
</div>



## Real-World Deployment

CORAL deployed on a BlueROV2 Heavy in a controlled pool (12 ft diameter, 5 ft
depth) with oyster shells and floating obstacle balls. Perception runs on-board
in real time; VLM queries reach cloud API endpoints asynchronously.

### Overhead view

- **Overhead View 1** — <https://www.youtube.com/watch?v=uur1PPlvJeU>
- **Overhead View 2** — <https://www.youtube.com/watch?v=xAjMP0Ewz1Y>

### First-person view

- **First Person View 1** — <https://www.youtube.com/watch?v=BRS6OG6R9Lg>
- **First Person View 2** — <https://www.youtube.com/watch?v=s47BGoXR_HU>


## Results

We evaluate CORAL against two baselines across 10 simulation environments of
varying topology complexity. All metrics are averaged over all environments.

| Method                | Coverage (%) ↑ | Time (s) ↓ | Collisions ↓ | VLM Calls ↓ |
|-----------------------|:--------------:|:----------:|:------------:|:-----------:|
| DREAM                 |     80.00      |   1513.2   |      9       |    1261     |
| CORAL w/o Low-Level   |     91.40      |    687.0   |     24       |     770     |
| **CORAL (Ours)**      |   **94.28**    |  **642.0** |   **0**      |   **547**   |

Headline gains over the previous state-of-the-art (DREAM):

- **+14.28 pp** coverage rate (80.00% → 94.28%)
- **−100%** collisions (9 → 0)
- **−57%** VLM calls (1261 → 547 per mission)


## BibTeX

```bibtex
@misc{wu2026coralcontextualreasoninglocal,
  title         = {CORAL: COntextual Reasoning And Local Planning in A Hierarchical VLM Framework for Underwater Monitoring},
  author        = {Zhenqi Wu and Yuanjie Lu and Xuesu Xiao and Xiaomin Lin},
  year          = {2026},
  eprint        = {2603.14786},
  archivePrefix = {arXiv},
  primaryClass  = {cs.RO},
  url           = {https://arxiv.org/abs/2603.14786}
}
```
