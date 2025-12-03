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

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import gamma

# Define dimensions from 1 to 20
dims = np.arange(1, 21)

# Calculate volumes
vol_ball = (np.pi**(dims/2)) / gamma(dims/2 + 1)
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
```


### Result

![Graph showing the collapse of the volume ratio](/images/bl.png)
*(Fig 1. The rapid decay of the ball's volume relative to the cube)*

**Analytical Insight:**
The decay is catastrophic. By dimension $d=10$, the ball occupies less than $0.3\%$ of the cube's volume. In the context of non-parametric statistics, this illustrates why neighborhood-based methods (like $k$-NN) struggle in high dimensions. The "neighborhood" effectively becomes empty, as the data is pushed into the sparse corners of the space.

---

## 2. Concentration of Measure: The "Orange Peel" Effect

A core tenet of high-dimensional probability is that mass concentrates near boundaries. If we consider a high-dimensional ball, the vast majority of its volume is located in a thin shell just beneath the surface.

We verify this by sampling points uniformly **inside** a unit ball in dimension $d=100$ and plotting the distribution of their radii (distance from the center).

```python
import numpy as np
import matplotlib.pyplot as plt

def sample_unit_ball(n_samples, d):
    # Muller method: Gaussian samples normalized + radial scaling
    X = np.random.normal(0, 1, size=(n_samples, d))
    
    # Project to sphere
    norms = np.linalg.norm(X, axis=1)
    
    # Inverse CDF sampling for radial part r ~ U^(1/d)
    # This pushes points toward the surface
    U = np.random.uniform(0, 1, size=n_samples)
    radii = U**(1/d) 
    
    return radii

d = 100
n_samples = 10000
radii = sample_unit_ball(n_samples, d)

plt.figure(figsize=(10, 6))
plt.hist(radii, bins=50, color='#e74c3c', alpha=0.8, density=True)
plt.title(f"Distribution of Radii for Uniform Points in $d={d}$", fontsize=14)
plt.xlabel("Radius $r$ (Distance from Center)")
plt.ylabel("Density")
plt.axvline(x=1.0, color='black', linestyle='--')
plt.xlim(0.8, 1.02) # Focus on the boundary
plt.grid(True, alpha=0.3)
plt.show()
```
### Analytical Insight
![Graph showing the collapse of the volume ratio](/images/radi.png)
*(Fig 2. Mass concentration near the boundary radius $r=1$)*

The histogram reveals that almost no points exist near the center (radius $< 0.9$). In dimension 100, 99% of the mass is located in the outer 5% of the shell. This numerical result validates the concentration inequalities studied in Phase 2: a Lipschitz function on a high-dimensional sphere is nearly constant because the measure itself is concentrated in a tiny region.

### 3. Projecting the Convex Set (Gaussian Universality)

Finally, we address the "Spoiler" from the inquiry: **Does the projection of a high-dimensional convex set look like a Gaussian?**

This is related to Klartag’s central limit theorem for convex sets. While the uniform measure on a sphere is not Gaussian, its marginals (projections onto 1D axes) converge to a Gaussian distribution as $d \to \infty$. We simulate this by projecting points from the surface of a sphere in $d=500$

### 3. Projecting the Convex Set (Gaussian Universality)

Finally, we address the "Spoiler" from the inquiry: **Does the projection of a high-dimensional convex set look like a Gaussian?**

This is related to Klartag’s central limit theorem for convex sets. While the uniform measure on a sphere is not Gaussian, its marginals (projections onto 1D axes) converge to a Gaussian distribution as $d \to \infty$. We simulate this by projecting points from the surface of a sphere in $d=500$.

```python
from scipy.stats import norm

d = 500
n_samples = 10000

# Sampling on the Sphere S^{d-1} (boundary of the ball)
X = np.random.normal(0, 1, size=(n_samples, d))
X_normalized = X / np.linalg.norm(X, axis=1, keepdims=True)

# Project onto the first coordinate and rescale
projected_data = X_normalized[:, 0] 
scaled_projection = projected_data * np.sqrt(d)

# Compare with Standard Normal
x_axis = np.linspace(-4, 4, 100)

plt.figure(figsize=(10, 6))
plt.hist(scaled_projection, bins=60, density=True, 
         color='#3498db', alpha=0.7, label='Projected Data')
plt.plot(x_axis, norm.pdf(x_axis), 'k--', linewidth=2, 
         label=r'Standard Normal $\mathcal{N}(0,1)$')

plt.title(f"1D Projection of Uniform Measure on Sphere ($d={d}$)", fontsize=14)
plt.xlabel("Projected Coordinate Value (Scaled)")
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()
```

#### Analytical Insight
![Graph showing the collapse of the volume ratio](/images/proj.png)
*(Fig 3. The projection of the sphere perfectly matches the Standard Normal distribution)*

> The overlay is nearly perfect. The projection of the high-dimensional geometry collapses into a standard normal distribution.
>
> This **geometric Central Limit Theorem** explains why Gaussian assumptions often hold in high-dimensional data analysis, even when the underlying data structure is merely convex and isotropic rather than strictly Gaussian.



