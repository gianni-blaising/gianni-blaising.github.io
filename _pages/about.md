---
permalink: /
title: "ROADMAP"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

---
layout: single
title: "Research Log: The Brunn-Minkowski Inequality"
author_profile: true
sidebar:
  nav: "docs"
---

<!-- ILLUSTRATION EN-TÊTE : Sorbonne / Mathématiques -->
![Sorbonne University](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Sorbonne_University_logo.svg/800px-Sorbonne_University_logo.svg.png)
*Student Researcher: Gianni Blaising | Sorbonne University | 4EU+ Alliance*

---


I am **Gianni Blaising**, a third-year undergraduate student in Mathematics at **Sorbonne University**.

This website serves as a research log documenting my academic journey and my preparation for the **BMST 2026 program** (Bachelor in Mathematics Student Team) within the 4EU+ Alliance.

---

# Project Roadmap: The Brunn-Minkowski Inequality

> **My Goal:** To investigate the Brunn-Minkowski inequality not just as a geometric theorem, but as a crossroads between **analysis**, **geometry**, and **probability**.

I have structured my work into four distinct phases, moving from fundamental tools to advanced applications.

<br>

## Phase 1: Foundations & "Crash Course"

![Minkowski Sum Visualization](https://upload.wikimedia.org/wikipedia/commons/thumb/2/26/Minkowski_sum.svg/800px-Minkowski_sum.svg.png)
*Visual intuition of the Minkowski Sum (A+B).*

To ensure rigor and refine my scientific writing skills, I initiated this project by consolidating the essential mathematical tools required for high-dimensional geometry. This preliminary phase covers:

* **Measure Theory**
    Revisiting the construction of the *Lebesgue measure* and the critical role of **Fubini's theorem** in slicing arguments.
* **Theory of Convex Bodies**
    Formalizing definitions of convexity, compact sets, and support functions in $\mathbb{R}^n$.
* **The Minkowski Sum**
    Building geometric intuition on how set addition behaves (regularity, smoothing properties) compared to standard union operations.

---

## Phase 2: The Functional Approach (Core Research)

![Log Concavity](https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Normal_Distribution_PDF.svg/1200px-Normal_Distribution_PDF.svg.png)
*The connection to probability: Log-concavity illustrated by the Gaussian distribution.*

Moving beyond classical geometric decompositions, I focus on the modern **analytical proof** of the inequality.

* **Key Tool:** The **Prékopa-Leindler inequality**.
* **Methodology:** Studying the proof by induction on dimension $n$, based on the advanced lecture notes of *Prof. Dario Cordero-Erausquin*. This approach highlights the deep connection between the inequality and the **log-concavity of measures**.

---

## Phase 3: High-Dimensional Phenomena

![Hypercube Projection](https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Tesseract-one-point-perspective-transparent.png/600px-Tesseract-one-point-perspective-transparent.png)
*Visualizing 4D+: Projection of a Tesseract (Hypercube).*

I extend the theoretical analysis with computational experiments to visualize **counter-intuitive behaviors** in high dimensions.

* **Simulations:** I replicate the *"Ball vs. Hypercube"* volume collapse example from the UE 4M073 course (Non-Parametric Statistics) taught by *Prof. Etienne Roquain*.
* **Concentration of Measure:** Illustrating how mass concentrates near the boundary of convex sets as $d \to \infty$.

---

## Phase 4: Perspectives & Isoperimetry

![Isoperimetric Problem](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Isoperimetric_inequality_visualisation.svg/800px-Isoperimetric_inequality_visualisation.svg.png)
*Geometric implications: Minimizing perimeter for a fixed volume.*

Finally, I connect these geometric insights to broader mathematical results.

* **The Isoperimetric Inequality**
    I will demonstrate how Brunn-Minkowski implies the isoperimetric inequality (*the Euclidean ball minimizes surface area for a fixed volume*).
* **Applications**
    Bridging the gap between pure mathematics and **Data Science** by exploring the **Johnson-Lindenstrauss Lemma**, a direct consequence of measure concentration.
