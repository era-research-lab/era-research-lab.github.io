---
layout: project
title: "Post-Fusion Bird's-Eye-View Feature Stabilization for Robust Multimodal 3D Detection"
permalink: /projects/pfs/
badge: IROS 2026
description: A lightweight post-fusion module that stabilizes BEV features for robust camera–LiDAR 3D detection under domain shift and sensor degradation.
authors:
  - { name: "Trung Tien Dong", url: "https://dongtrung28.github.io/" }
  - { name: "Dev Thakkar" }
  - { name: "Arman Sargolzaei", url: "https://scholar.google.com/citations?user=bwI_W-QAAAAJ&hl=en" }
  - { name: "Xiaomin Lin", url: "https://xiaominlin.github.io/" }
affiliations: "Electrical & Computer Engineering · Mechanical Engineering — University of South Florida"
links:
  - { label: "arXiv", url: "https://arxiv.org/abs/2603.05623", icon: "ai ai-arxiv" }
  - { label: "Video", url: "https://youtu.be/-4BJK7Oi_yM", icon: "fab fa-youtube" }
  - { label: "Code (coming soon)", url: "#", icon: "fab fa-github" }
---

<figure>
  <img src="{{ '/assets/images/projects/pfs.png' | relative_url }}" alt="PFS architecture overview">
  <figcaption>
    Overall PFS architecture. A lightweight Feature Stabilizer is placed between the
    fused BEV feature map and the frozen detection head. It applies (1) channel shift
    normalization, (2) spatial reliability suppression, and (3) degradation-aware gated
    residual correction with semantic and geometric experts to produce a stabilized
    feature map, which is then fed to the unchanged detection head. All stabilizer
    blocks are identity-initialized for safe deployment.
  </figcaption>
</figure>

## Abstract

Camera–LiDAR fusion is widely used in autonomous driving to enable accurate 3D object
detection. However, bird's-eye-view (BEV) fusion detectors can degrade significantly
under domain shift and sensor failures, limiting reliability in real-world deployment.
Existing robustness approaches often require modifying the fusion architecture or
retraining specialized models, making them difficult to integrate into already deployed
systems.

We propose a **Post-Fusion Stabilizer (PFS)**, a lightweight module that operates on
intermediate BEV representations of existing detectors and produces a refined feature
map for the original detection head. The design stabilizes feature statistics under
domain shift, suppresses spatial regions affected by sensor degradation, and adaptively
restores weakened cues through residual correction. Designed as a near-identity
transformation, PFS preserves performance while improving robustness under diverse
camera and LiDAR corruptions. Evaluations on the nuScenes benchmark demonstrate that PFS
achieves state-of-the-art results in several failure modes, notably improving camera
dropout robustness by **+1.2%** and low-light performance by **+4.4% mAP** while
maintaining a lightweight footprint of only **3.3M parameters**.

## Methodology

<div class="callout">
  <p class="note-todo">Detailed method description coming soon. See the <a href="https://arxiv.org/abs/2603.05623" target="_blank" rel="noopener">arXiv paper</a> for the full formulation.</p>
</div>

<div class="placeholder-box" style="margin-top:1.5rem;">Method overview figure — TODO</div>

## Video

<div class="video-embed">
  <iframe src="https://www.youtube.com/embed/-4BJK7Oi_yM"
          allow="autoplay; encrypted-media" allowfullscreen title="PFS video"></iframe>
</div>

## Results

<div class="callout">
  <p class="note-todo">Quantitative results and qualitative comparisons coming soon.</p>
</div>

## BibTeX

```bibtex
@misc{dong2026postfusionbirdseye,
  title={Post Fusion Bird's Eye View Feature Stabilization for Robust Multimodal 3D Detection},
  author={Trung Tien Dong and Dev Thakkar and Arman Sargolzaei and Xiaomin Lin},
  year={2026},
  eprint={2603.05623},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  url={https://arxiv.org/abs/2603.05623}
}
```
