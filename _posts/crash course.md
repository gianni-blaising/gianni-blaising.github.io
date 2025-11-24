title: "Foundations and crash course"
date: 2025-11-25
permalink: /posts/crash course/
tags:


# Phase 1: Foundations & Crash Course

Before tackling the Brunn-Minkowski inequality, we must establish a rigorous dictionary between geometry and analysis. This section synthesizes the essential prerequisites, ranging from the construction of volume to the algebraic structure of convex sets.

## 1. Measure Theory: From Intuition to Rigor
*Based on the lecture notes of Prof. Jean-François Le Gall.*

To define the "volume" of a set in $\mathbb{R}^n$, we cannot simply assign a number to every subset. To avoid paradoxes (like the Banach-Tarski paradox, where a ball can be cut and reassembled into two balls of the same volume), we must restrict our attention to a specific class of "measurable" sets. The construction proceeds in three logical steps:

### Step 1: The Outer Measure ($\lambda^*$)
We start with the intuitive notion that the volume of a rectangular box is the product of its side lengths. For any arbitrary subset $A \subset \mathbb{R}^n$, we define its **Lebesgue outer measure** $\lambda^*(A)$ by covering $A$ with a countable collection of boxes and taking the infimum of their total volume:

$$
\lambda^*(A) = \inf \left\{ \sum_{i=1}^\infty \text{Vol}(R_i) \mid A \subset \bigcup_{i=1}^\infty R_i, \ R_i \text{ are boxes} \right\}
$$

While $\lambda^*$ is defined for *all* subsets, it lacks the critical property of **countably additivity** (the measure of a union of disjoint sets is the sum of their measures), which is essential for taking limits.

### Step 2: Carathéodory's Criterion & The $\sigma$-algebra
To recover additivity, we restrict ourselves to the **Borel $\sigma$-algebra**, denoted $\mathcal{B}(\mathbb{R}^n)$. A set $E$ is deemed "measurable" (Carathéodory's criterion) if it splits every other set additively:

$$
\forall A \subset \mathbb{R}^n, \quad \lambda^*(A) = \lambda^*(A \cap E) + \lambda^*(A \cap E^c)
$$

This restriction defines the **Lebesgue Measure** $\lambda$. For any $E \in \mathcal{B}(\mathbb{R}^n)$, $\lambda(E)$ behaves exactly as "volume" should: it is translation-invariant and countably additive.

### Step 3: Integration and Fubini’s Theorem
The bridge between high-dimensional geometry and 1-dimensional analysis is **Fubini’s Theorem**. It allows us to compute the volume of a set $K \subset \mathbb{R}^{n+1}$ by integrating the volume of its slices.

If we write $z = (x, t)$ where $x \in \mathbb{R}^n$ and $t \in \mathbb{R}$, and let $K_t = \{ x \in \mathbb{R}^n \mid (x,t) \in K \}$ be the section of $K$ at height $t$, then:

$$
\text{Vol}_{n+1}(K) = \int_{-\infty}^{+\infty} \text{Vol}_n(K_t) \, dt
$$

> **Key Insight:** This "slicing principle" is the primary mechanism used in the geometric proof of Brunn-Minkowski. It reduces an $(n+1)$-dimensional problem to an integration over $n$-dimensional cross-sections.

---

## 2. Topological Prerequisites for Geometry
To discuss "Convex Bodies," we need specific topological tools in the metric space $(\mathbb{R}^n, \|\cdot\|)$.

* **Open and Closed Sets:** A set is **closed** if it contains all its limit points. This is crucial because we want our geometric shapes to include their boundaries (e.g., a solid ball includes its shell).
* **Boundedness:** A set is **bounded** if it can be contained within a ball of finite radius.
* **Compactness (Heine-Borel):** In $\mathbb{R}^n$, a subset is **compact** if and only if it is both **closed and bounded**.
    * *Why it matters:* Compactness ensures that continuous functions (like distance or projection) attain their maximum and minimum values on the set. This allows us to talk about "extremal points" or the "width" of a body without ambiguity.

---

## 3. The Theory of Convex Bodies
The central objects of study in the Brunn-Minkowski theory are **Convex Bodies**.

**Definition:** A subset $K \subset \mathbb{R}^n$ is called a **Convex Body** if it satisfies three conditions:

1.  **Compactness:** $K$ is closed and bounded.
2.  **Non-empty interior:** $K$ has volume (strictly speaking, some definitions just require $K \neq \emptyset$, but for volume inequalities, we assume full dimension).
3.  **Convexity:** For any two points $x, y \in K$, the entire line segment connecting them lies within $K$:
    $$
    \forall t \in [0, 1], \quad (1-t)x + ty \in K
    $$

We denote the set of all convex bodies in $\mathbb{R}^n$ as $\mathcal{K}^n$.

> **Geometric Intuition:** A set is convex if it has "no dents." If you wrap a rubber band around a convex set, the band touches the boundary everywhere.

---

## 4. The Minkowski Sum
This is the fundamental operation of the theory. Unlike the standard union ($A \cup B$), which simply places two sets side-by-side, the **Minkowski Sum** is an **algebraic addition** of the sets themselves.

### Definition
For two sets $A, B \subset \mathbb{R}^n$, their Minkowski sum is defined pointwise:

$$
A + B = \{ a + b \mid a \in A, b \in B \}
$$

### Geometric Intuition & Deep Insight
The Minkowski sum can be visualized as **"sweeping"** one set around the other. If you take set $A$ and place a copy of set $B$ centered at every point of $A$, the union of all these copies is $A+B$.

**Why is this operation profound?**

1.  **Regularization (Smoothing):** This is the most critical intuition for analysis. If $A$ is a "rough" set (e.g., a square with sharp corners) and $B$ is a "smooth" set (e.g., a ball), their sum $A+B$ will be smooth. The ball "rounds off" the corners of the square.
    * *In analysis terms:* This is strictly analogous to the **convolution** of functions. Just as convolving a discontinuous function with a Gaussian makes it smooth ($C^\infty$), adding a Euclidean ball to a set creates a smooth boundary.
2.  **Linear Structure:** The Minkowski sum gives the space of convex bodies a "semi-group" structure. It allows us to treat geometric shapes almost like numbers that can be added and scaled.

### Illustration



* **Top Left (A):** A Square (Sharp corners, non-smooth).
* **Top Right (B):** A Circle (Smooth, constant curvature).
* **Bottom (A+B):** The resulting shape is a "rounded square." Notice how the sharp vertices of the square have been replaced by circular arcs with the radius of $B$. The sum has inherited the smoothness of $B$ and the global structure of $A$.
