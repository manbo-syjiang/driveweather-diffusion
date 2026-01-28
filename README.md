# DriveWeather: A Motion-Consistent Dynamic Weather Synthesis Framework via Video-to-Video Diffusion for Autonomous Driving

<p align="center">
  <img src="assets/figures/teaser.png" width="95%" />
</p>

<p align="center">
  <a href="#overview">Overview</a> •
  <a href="#method">Method</a> •
  <a href="#experiments">Experiments</a> •
  <a href="#installation">Installation</a> •
  <a href="#data-preparation">Data</a> •
  <a href="#training">Training</a> •
  <a href="#inference">Inference</a> •
  <a href="#evaluation">Evaluation</a> •
  <a href="#citation">Citation</a>
</p>

---

## Overview

DriveWeather is a **video-to-video conditional diffusion** framework for synthesizing **realistic, temporally continuous, and ego-motion-consistent** dynamic weather effects (e.g., rain streaks and snow particles) in autonomous driving videos.  
It explicitly models **ego-motion states** and **scene structure** to generate **motion-consistent dynamic weather** while preserving the underlying scene content.

### Abstract
> In autonomous driving, large-scale scene data spanning diverse weather conditions are essential for improving the robustness of perception models under challenging weather conditions. However, collecting such real-world driving data is prohibitively expensive. Existing driving-scene generation methods primarily focus on scene-structure synthesis and typically fail to model temporally continuous weather dynamics, such as rain streaks and snow particles evolving coherently across frames, while existing methods for synthesizing dynamic weather struggle to synthesize ego-motion-consistent weather dynamics (e.g., rain streaks and snow particles showing ego-motion-consistent visual drift) in driving videos. We propose DriveWeather, a video-to-video conditional diffusion framework for dynamic weather synthesis in autonomous driving. We further design a Motion–Structure Perceptor (MSP) that perceives ego-motion and scene structure and explicitly model ego-motion states and dynamic weather, enabling motion-consistent weather synthesis. Moreover, to suppress hallucinated artifacts in large low-texture regions, we introduce a Dual-Adversarial Calibration Block (DACB) to calibrate the generation process for stable outputs. Extensive experiments on multiple datasets demonstrate that DriveWeather achieves robust overall performance in weather semantic consistency, structural fidelity, and motion consistency. Importantly, DriveWeather effectively perceives ego-motion, preserves the underlying scene structure, and synthesizes realistic, motion-consistent dynamic weather effects that better match real driving scenarios. This provides high-quality synthetic data for training and evaluating autonomous-driving perception models and helps improve their robustness across diverse weather conditions.

---

## Method

<p align="center">
  <img src="assets/figures/teaser.jpg" width="95%" />
</p>
<p align="center"><em>Figure 1. Overview of DriveWeather. (Replace this caption with your paper caption.)</em></p>

**Core components**
- **MSP**: perceives ego-motion states and scene structure; provides motion-aware conditions for diffusion.
- **DACB**: calibrates generation and reduces artifacts/hallucinations in low-texture regions.

---

## Experiments

### Qualitative Results
<p align="center">
  <img src="assets/figures/fig2.png" width="95%" />
</p>
<p align="center"><em>Figure 2. Qualitative comparison / main results.</em></p>

<p align="center">
  <img src="assets/figures/fig3.png" width="95%" />
</p>
<p align="center"><em>Figure 3. Motion-consistent weather dynamics (ego-motion-consistent visual drift).</em></p>

### Ablations / Analysis
<p align="center">
  <img src="assets/figures/fig4.png" width="95%" />
</p>
<p align="center"><em>Figure 4. Ablation on MSP / motion modeling.</em></p>

<p align="center">
  <img src="assets/figures/fig5.png" width="95%" />
</p>
<p align="center"><em>Figure 5. Ablation on DACB / artifact suppression.</em></p>

### Downstream Perception Robustness
<p align="center">
  <img src="assets/figures/fig6.png" width="95%" />
</p>
<p align="center"><em>Figure 6. Downstream detection robustness evaluation (e.g., DAWN mAP@0.5).</em></p>

---

## Installation

### 1) Clone
```bash
git clone https://github.com/<your-org-or-name>/DriveWeather.git
cd DriveWeather
