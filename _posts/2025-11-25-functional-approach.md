title: "The Functional Approach to Brunn-Minkowski"
date: 2025-11-25
permalink: /posts/2025/11/functional-approach/
tags:

mathematics

analysis

convex-geometry
mathjax: true

To prove the inequality, we move away from classical geometry to consider measurable functions on $\mathbb{R}^n$. The core tool is the Prékopa-Leindler inequality, a reverse form of Hölder's inequality.

1. The Geometric Condition

Let $\lambda \in (0,1)$. We consider three non-negative measurable functions $f, g, h$ satisfying the following convexity condition for all $x, y \in \mathbb{R}^n$:

$$h((1-\lambda)x + \lambda y) \ge f(x)^{1-\lambda} g(y)^\lambda$$

This condition implies that the function $h$ is "larger" than the geometric mean of $f$ and $g$ along the segment connecting any two points.

2. The Integral Inequality

The theorem states that this local geometric property is preserved by integration over the whole space:

$$\int_{\mathbb{R}^n} h(x) dx \ge \left( \int_{\mathbb{R}^n} f(x) dx \right)^{1-\lambda} \left( \int_{\mathbb{R}^n} g(x) dx \right)^\lambda$$

3. Connecting to Sets

To recover the Brunn-Minkowski inequality for convex sets $A$ and $B$, we simply choose indicator functions:

Let $f(x) = \mathbf{1}_A(x)$

Let $g(x) = \mathbf{1}_B(x)$

Let $h(x) = \mathbf{1}_{(1-\lambda)A + \lambda B}(x)$

The integral of an indicator function is simply the volume (Lebesgue measure) of the set. The inequality immediately yields:

$$\text{Vol}((1-\lambda)A + \lambda B) \ge \text{Vol}(A)^{1-\lambda} \text{Vol}(B)^\lambda$$

Visual Interpretation

The power of this approach is that it handles the "smoothing" effect of the Minkowski sum naturally through the convolution-like structure of the integrals.

Figure 1: Numerical verification of volume concentration in high dimensions (Simulation Python).
