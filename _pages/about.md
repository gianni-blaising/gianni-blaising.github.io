---
permalink: /
title: "ROADMAP"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


![Convex Geometry](../images/convex%20geom.png)
---



I am **Gianni Blaising**, a third-year undergraduate student in Mathematics at **Sorbonne University**.

This website serves as a research log documenting my academic journey and my preparation for the **BMST 2026 program** within the 4EU+ Alliance.

All primary sources and foundational materials supporting this research are listed in the 'References' section.



---

# Project Roadmap: The Brunn-Minkowski Inequality

**My Goal:** To analyze the Brunn-Minkowski inequality not just as a geometric curiosity, but as the pivotal interface between convex geometry, probability, and high-dimensional statistics.

I have organized my learning path into four phases. Below is the progress log of this journey, moving from fundamental definitions to computational verification and advanced applications.

---

### ✅ Phase 1: Foundations & The "Crash Course"
*(Status: Completed)*

To ensure rigor, I began by consolidating the essential mathematical frameworks required for convex geometry. This phase serves as the theoretical bedrock for the project.

* **Measure Theory:** Revisiting the construction of the Lebesgue measure and the crucial role of Fubini’s theorem in slicing arguments (based on Prof. Le Gall’s notes).
* **Convex Bodies:** Formalizing compactness, support functions, and the topology of sets in $\mathbb{R}^n$.
* **The Minkowski Sum:** Building geometric intuition on set addition and its regularizing (smoothing) properties.

### ✅ Phase 2: Convexity & Concentration
*(Status: Completed — Joint work with Elias Touil)*

This phase bridges the gap between geometry and statistics. Moving beyond classical intuition, we adopted the functional analysis formalism to address the "Curse of Dimensionality."

* **Log-Concavity:** Extending Brunn-Minkowski to probability measures via the **Prékopa-Leindler inequality**.
* **Concentration of Measure:** Demonstrating how convexity creates topological stability, forcing mass to concentrate on the boundaries of high-dimensional sets.
* **Statistical Applications:** Explaining why convex relaxations (like the **LASSO**) work in high dimensions ($p \gg n$) thanks to the geometry of tangent cones and "pointy" balls.

### ✅ Phase 3: Computational Verification
*(Status: Completed)*

After the abstraction of Phase 2, I implemented Python simulations to ground these concepts numerically and visualize counter-intuitive high-dimensional behaviors.

* **Volume Collapse:** Replicating experiments from **Prof. Etienne Roquain’s** course (UE 4M073) to show the vanishing volume of the Euclidean ball relative to the hypercube as $d \to \infty$.
* **The "Spiky" Cube:** Visualizing how the geometry of space changes, making distance and orthogonality behave differently than in $\mathbb{R}^3$.

### 🔄 Phase 4: Perspectives & Isoperimetry
*(Status: Upcoming)*

The final phase will connect these insights to broader mathematical results.

* **The Isoperimetric Inequality:** Demonstrating how Brunn-Minkowski implies that the Euclidean ball minimizes surface area for a fixed volume.
* **Data Science Bridges:** Exploring the **Johnson-Lindenstrauss Lemma** as a direct consequence of measure concentration, linking this research to dimensionality reduction techniques.
