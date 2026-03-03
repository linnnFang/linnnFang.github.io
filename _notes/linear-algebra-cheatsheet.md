---
title: "Linear Algebra Cheat Sheet"
excerpt: "Key identities and decompositions for quick reference."
tags:
  - Math
  - Linear Algebra
toc: true
---

## Matrix Decompositions

**SVD:** Any matrix $A \in \mathbb{R}^{m \times n}$ can be decomposed as $A = U \Sigma V^\top$.

**Eigendecomposition:** For symmetric $A$: $A = Q \Lambda Q^\top$.

**Cholesky:** For positive definite $A$: $A = L L^\top$.

## Useful Identities

- $(AB)^\top = B^\top A^\top$
- $(A^{-1})^\top = (A^\top)^{-1}$
- $\text{tr}(ABC) = \text{tr}(CAB) = \text{tr}(BCA)$
- $\det(AB) = \det(A)\det(B)$
