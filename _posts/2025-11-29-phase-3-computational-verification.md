---
title: "Phase 3: Computational Verification of High-Dimensional Phenomena"
date: 2025-11-29
permalink: /posts/phase-3-computational-verification/
categories: [Research, Mathematics, Simulation]
tags: [High-Dimensional Probability, Python, Convex Geometry, Curse of Dimensionality]
math: true
---

# High-Dimensional Geometry: The Empty Ball and the Spiky Cube

**Phase 3 — Computational Experiments**

> **Abstract**
> Following the theoretical abstractions of Phase 2, this report transitions into computational verification. We ground the complex properties of high-dimensional spaces—specifically Log-Sobolev inequalities and concentration of measure—using numerical experiments. By replicating geometric examples from the *UE 4M073 Non-Parametric Statistics* course (Prof. Etienne Roquain), we visualize three counter-intuitive behaviors: the collapse of volume in hyperspheres, the "orange peel" concentration of measure, and the emergence of Gaussian distributions from convex projections.

---

## 1. The Curse of Dimensionality: Ball vs. Hypercube

In dimension $d=2$, a unit circle inscribed in a square covers the majority of the area ($\pi/4 \approx 78.5\%$). Intuition suggests that as we add dimensions, the ball should continue to fill the cube comfortably. However, the geometry of high-dimensional space defies this 3D intuition. The corners of the hypercube become vast, "spiky" regions that leave almost no room for the central ball.

The following simulation computes the volume ratio between the unit ball $\mathcal{B}_d$ and the unit cube $\mathcal{C}_d = [-1, 1]^d$ as $d$ increases.

```markdown
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import gamma

# Define dimensions from 1 to 20
dims = np.arange(1, 21)

# Calculate volumes
# Vol(Ball) = pi^(d/2) / gamma(d/2 + 1)
vol_ball = (np.pi**(dims/2)) / gamma(dims/2 + 1)

# Vol(Cube) = 2^d (since side length is 2)
vol_cube = 2.0**dims

ratios = vol_ball / vol_cube

# Visualization
plt.figure(figsize=(10, 6))
plt.plot(dims, ratios, marker='o', linewidth=2, color='#2c3e50')
plt.title("Volume Ratio: Unit Ball vs. Unit Hypercube", fontsize=14)
plt.xlabel("Dimension $d$")
plt.ylabel(r"Volume Ratio $\frac{Vol(\mathcal{B}_d)}{Vol(\mathcal{C}_d)}$")
plt.grid(True, alpha=0.3)
plt.xticks(dims)
plt.axhline(0, color='black', linewidth=0.8)
plt.show()
