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

> **My Goal:** To analyze the Brunn-Minkowski inequality as the pivotal interface between convex geometry and functional analysis, establishing the theoretical framework required for high-dimensional probability.

I have structured my work into four distinct phases, moving from fundamental tools to advanced applications.

<br>

## Phase 1: Foundations & "Crash Course"

To ensure rigor and refine my scientific writing skills, I initiated this project by consolidating the essential mathematical tools required for high-dimensional geometry. This preliminary phase covers:

* **Measure Theory**
    Revisiting the construction of the *Lebesgue measure* based on *Prof. Jean-François Le Gall's* lecture notes, and emphasizing the critical role of **Fubini's theorem** in slicing arguments.
* **Theory of Convex Bodies**
    Formalizing definitions of convexity, compact sets, and support functions in $\mathbb{R}^n$.
* **The Minkowski Sum**
    Building geometric intuition on how set addition behaves (regularity, smoothing properties) compared to standard union operations.

---

## Phase 2: The Functional Approach (Core Research)

Moving beyond classical geometric decompositions, I adopt the **functional analysis formalism**, which constitutes the prevailing framework in contemporary research.

* **Key Tool:** The **Prékopa-Leindler inequality**. This theorem allows working directly with **log-concave measures**, providing a robust substitute for geometric intuition which becomes unreliable in high dimensions.
* **Methodology:** Following Prof. Dario Cordero-Erausquin’s notes, I focus on the **Minkowski functional (gauge)**. This tool establishes a structural bijection between convex bodies and sub-linear functions, effectively translating geometric problems into analytical ones. Mastering this formalism is a prerequisite for investigating **concentration of measure**, aligning with the current standards in high-dimensional probability.
---

## Phase 3: High-Dimensional Phenomena

I extend the theoretical analysis with computational experiments to visualize **counter-intuitive behaviors** in high dimensions.

* **Simulations:** I replicate the *"Ball vs. Hypercube"* volume collapse example from the UE 4M073 course (Non-Parametric Statistics) taught by *Prof. Etienne Roquain*.
* **Concentration of Measure:** Illustrating how mass concentrates near the boundary of convex sets as $d \to \infty$.

---

## Phase 4: Perspectives & Isoperimetry

Finally, I connect these geometric insights to broader mathematical results.

* **The Isoperimetric Inequality**
    I will demonstrate how Brunn-Minkowski implies the isoperimetric inequality (*the Euclidean ball minimizes surface area for a fixed volume*).
* **Applications**
    Bridging the gap between pure mathematics and **Data Science** by exploring the **Johnson-Lindenstrauss Lemma**, a direct consequence of measure concentration.
