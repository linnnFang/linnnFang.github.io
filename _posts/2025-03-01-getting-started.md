---
title: "Getting Started with Convex Optimization in Python"
date: 2025-03-01
categories:
  - Tutorial
tags:
  - Optimization
  - Python
  - CVXPY
toc: true
toc_sticky: true
---

A quick introduction to solving optimization problems with CVXPY.

## The Problem

Consider a classic mean-variance optimization:

$$\min_w \; \frac{1}{2} w^\top \Sigma w - \lambda \mu^\top w$$

## Python Implementation

```python
import numpy as np
import cvxpy as cp

n = 10
mu = np.random.randn(n) * 0.1
Sigma = np.random.randn(n, n)
Sigma = Sigma.T @ Sigma / n

w = cp.Variable(n)
objective = cp.Minimize(0.5 * cp.quad_form(w, Sigma) - 0.5 * mu @ w)
constraints = [cp.sum(w) == 1, w >= 0]

prob = cp.Problem(objective, constraints)
prob.solve()
print(f"Optimal weights: {w.value.round(4)}")
```
