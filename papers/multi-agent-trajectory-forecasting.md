# Multi-Agent Trajectory Forecasting in Synthetic Urban Environments

**Authors:** Leonard Klein, Maria Rodriguez, Priya Sharma

**Affiliation:** GidronAI Inc., Toronto, Canada

**Date:** May 2026

**Status:** In Preparation

---

## Abstract

Accurate trajectory forecasting of pedestrians and vehicles is critical for safe autonomous navigation. Existing forecasting models are trained on datasets with limited scene diversity and agent density, leading to poor generalization in crowded or unusual layouts. We propose using the GidronAI engine to generate synthetic urban environments with controllable agent populations ranging from 5 to 200 agents per scene, enabling systematic study of forecasting performance as a function of crowd density, interaction topology, and scene geometry. Our synthetic trajectories are generated using calibrated social force and ORCA models with parameters fit to real-world pedestrian tracking data (ETH/UCY, Stanford Drone). We show that augmenting real trajectory datasets with our synthetic data improves state-of-the-art forecasting models (Trajectron++, AgentFormer) by 8--15% on ADE/FDE metrics, with the largest gains in high-density scenarios (>50 agents) where real data is scarce. We release a benchmark of 100K synthetic trajectories across 500 unique scene configurations.

## Key Contributions

1. A calibration pipeline that fits GidronAI agent behavior parameters to real pedestrian tracking datasets.
2. Systematic analysis of forecasting model performance versus agent density, showing a critical degradation threshold at ~80 agents/scene for current architectures.
3. A synthetic trajectory benchmark (GidronTraj-100K) with full scene context, interaction graphs, and ground-truth future paths.
4. Evidence that synthetic trajectory augmentation is most effective for rare interaction patterns (merging flows, counter-flow, bottlenecks).

## Planned Experiments

- Density sweep: 5, 10, 25, 50, 100, 200 agents across 5 scene types
- Cross-dataset transfer: train on synthetic, evaluate on ETH/UCY and Stanford Drone
- Ablation: social force vs. ORCA vs. recorded replay

## Citation

```bibtex
@article{klein2026multiagent,
  title={Multi-Agent Trajectory Forecasting in Synthetic Urban Environments},
  author={Klein, Leonard and Rodriguez, Maria and Sharma, Priya},
  journal={In preparation},
  year={2026}
}
```
