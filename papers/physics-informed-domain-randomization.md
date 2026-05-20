# Physics-Informed Domain Randomization for Sim-to-Real Transfer

**Authors:** Leonard Klein, Yuki Tanaka, David Osei

**Affiliation:** GidronAI Inc., Toronto, Canada

**Date:** April 2026

**Status:** Preprint

---

## Abstract

Domain randomization is a widely adopted technique for bridging the visual gap between simulated and real-world imagery. However, naive randomization of physical parameters (e.g., object masses, friction coefficients, lighting conditions) often produces implausible configurations that degrade learned policy robustness. We introduce Physics-Informed Domain Randomization (PIDR), a constrained randomization strategy that samples simulation parameters from distributions anchored to measured real-world priors while enforcing physical consistency via lightweight constraint solvers. PIDR operates within the GidronAI synthesis engine and modulates five randomization axes: material reflectance, rigid-body dynamics, articulated joint limits, atmospheric scattering, and sensor noise. In manipulation and navigation benchmarks, policies trained with PIDR achieve 23% higher zero-shot sim-to-real transfer success rates compared to unconstrained domain randomization baselines, while requiring 40% fewer training environments to reach equivalent performance.

## Key Contributions

1. Formalization of physics-informed randomization as a constrained sampling problem over scene parameters.
2. A differentiable constraint layer that rejects physically implausible parameter combinations at generation time.
3. Integration with the GidronAI engine's YAML configuration system for reproducible experiment specification.
4. Evaluation on three sim-to-real benchmarks: tabletop manipulation (RLBench), indoor navigation (Habitat), and autonomous driving (CARLA transfer).

## Results Summary

| Benchmark | Standard DR | PIDR (Ours) | Real-Only |
|-----------|-------------|-------------|-----------|
| RLBench (avg. success %) | 48.3 | 71.6 | 82.1 |
| Habitat PointNav (SPL) | 0.52 | 0.68 | 0.74 |
| CARLA Transfer (driving score) | 61.4 | 79.2 | 85.7 |

## Citation

```bibtex
@article{klein2026pidr,
  title={Physics-Informed Domain Randomization for Sim-to-Real Transfer},
  author={Klein, Leonard and Tanaka, Yuki and Osei, David},
  journal={arXiv preprint},
  year={2026}
}
```
