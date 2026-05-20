# Scalable Procedural Scene Synthesis for Autonomous Driving

**Authors:** Leonard Klein, Arjun Mehta, Sarah Chen

**Affiliation:** GidronAI Inc., Toronto, Canada

**Date:** May 2026

**Status:** Preprint

---

## Abstract

Training robust perception models for autonomous driving requires diverse, large-scale annotated datasets that capture the long tail of real-world scenarios. Manual data collection and labeling is prohibitively expensive and inherently limited in coverage. We present a scalable procedural scene synthesis framework that generates physically plausible urban environments with automatic ground-truth annotations. Our approach combines parametric road network generation, rule-based structure placement, and stochastic prop scattering to produce diverse intersection, highway, and residential scenes. Each scene is rendered with configurable weather, lighting, and camera rigs, yielding pixel-perfect RGB, depth, semantic segmentation, and instance masks. We demonstrate that models pre-trained on our synthetic data and fine-tuned on 10% of real data match the performance of models trained on 100% real data across the nuScenes and KITTI benchmarks. The framework generates annotated scenes at a rate of 850 frames per GPU-hour on commodity hardware, enabling dataset scales previously accessible only to large industry labs.

## Key Contributions

1. A procedural scene graph representation that decouples geometry, materials, and layout into independently randomizable layers.
2. A physics-aware placement algorithm that enforces structural coherence (e.g., buildings do not intersect roads, traffic signs face correct lanes).
3. Empirical validation showing synthetic pre-training closes 91% of the sim-to-real gap on 3D object detection (nuScenes val mAP).
4. An open-source implementation integrated into the GidronAI engine.

## Method Overview

The pipeline consists of five stages:

1. **Road Network Generation** -- L-system grammar with intersection templates and lane-level topology.
2. **Structure Placement** -- Constraint-satisfaction placement of buildings, barriers, and terrain features using scene-type priors.
3. **Prop Scattering** -- Poisson-disk sampling with density maps for vegetation, street furniture, and vehicles.
4. **Lighting & Weather** -- Physically-based sky model with parametric cloud cover, rain particle systems, and time-of-day sun position.
5. **Multi-Sensor Rendering** -- Synchronized RGB, LiDAR, depth, and segmentation from configurable sensor rigs.

## Results Summary

| Model | Real Data | Synthetic Pre-train | nuScenes val mAP |
|-------|-----------|---------------------|-------------------|
| CenterPoint | 100% | No | 59.6 |
| CenterPoint | 10% | No | 41.2 |
| CenterPoint | 10% | Yes (ours) | 58.1 |
| BEVFusion | 100% | No | 68.5 |
| BEVFusion | 10% | Yes (ours) | 66.9 |

## Citation

```bibtex
@article{klein2026scalable,
  title={Scalable Procedural Scene Synthesis for Autonomous Driving},
  author={Klein, Leonard and Mehta, Arjun and Chen, Sarah},
  journal={arXiv preprint},
  year={2026}
}
```
