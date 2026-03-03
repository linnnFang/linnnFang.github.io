---
title: "ODE Notes (Undergraduate)"
excerpt: "Ordinary Differential Equations notes."
toc: true
---

# MATH 119B

[solution to textbook 119.pdf](MATH%20119B/solution_to_textbook_119.pdf)

[119textbook.pdf](MATH%20119B/119textbook.pdf)

# Chapter1 Linear system

## stability theory

$$
x(t) = e^{At}x_0
$$

The set of mappings $e^{At}: \mathbb{R^n} \to \mathbb{R^n}$  may be regarded as describing teh motion of points  $x_0\in \mathbb{R^n}$ along trajectories of $\dot{x} = Ax$. This set of mappings is called **the flow of the linear system** $\dot{x} = Ax$

**Definition2**: If all eigenvalues of teh $n \times n$ matrix A have non-zero real part, then the flow $e^{At} : \mathbb{R^n} \to \mathbb{R^n}$ is called a hyperbolic flow and $\dot{x} = Ax$ is called a hyperbolic linear system

the **mapping** $\phi_t = e^{At}$ properties of the flow for $all \space x \in \mathbb{R^n}$:

1. $\phi_0(x) = x$
2. $\phi_s(\phi_t(x)) = \phi_{s+t}(x)$
3. $\phi_{-t}(\phi_t(x)) = \phi_t(\phi_{-t}) = x \hspace{1cm} for  \space t\in \mathbb{R}$

*Remark:* 

- the `property 1` follows form the definiyion of $e^{At}$
- `property 2` follows from proposition 2 in section 1.3 of C1
    
    ![Proposition 2](/assets/images/notes/ode/Screenshot_2025-02-09_at_2_07_40_PM.png)
    
- `property 3` follows form Corollary 2 in section 1.3 of C1
    
    ![Corollary 2](assets/images/notes/ode/Screenshot_2025-02-09_at_2.08.02_PM.png)
    

# Chapter 2 Nonlinear systems

## 2.1 Preliminary Concepts and Definitions

Autonomous equation: 

$$
\dot{x} = f(x) \qquad (1)
$$

Non-autonomous equation

$$
\dot{x} = f(x,t) \qquad (2)
$$

if $f(x)$ is ingrateable, then the solution might exist but does not guarantee the uniqueness of the solution.

**Example1** : $x = t^3$ and $x = 0$

**Remark**:

- $f(x)$ is continuous at x=0, but not differentiable
- when $\dot{x} = f(x)$  is well defined and continuous for all $x \in \mathbb{R}$, the solution $x(t)$ might become unbounded. Solution might **only exist on some proper subinterval.**

**Example2:** 

$$
\dot{x} = x^2 \\x(0) = 1
$$

The interval $(-\infty, 1)$is the **maximal interval of existence** of the solution of the initial value problem.

- here, because $t = 0 \notin (1,\infty)$, so we didnt consider this.

**Definition 1:** The function $f: \mathbb{R^n} \to \mathbb{R^n}$ is *differentiable* at $x_0 \in \mathbb{R}$ if there is a linear transformation$Df(x_0) \in L(\mathbb{R^n)}$ **that satisfies:

$$
\lim_{|h| \to 0} \frac{|f(x_0+h)-f(x_0)-Df(x_0)h|}{|h|} = 0
$$

The linear transformation $Df(x_0)$is called the ***derivative** of $f$* *at* Xo.

![Theorem 1](assets/images/notes/ode/Screenshot_2025-02-07_at_12.08.56_PM.png)

**Definition 2:** Soppose $V_1$ and $V_2$ are two norm linear spaces with respective norms $||.||_1$ and $||.||_2$ Then, $F: V_1 \to V_2$ is continuous at $x_0 \in V_1$ if for all $\epsilon >0$, tehre exists a $\delta>0$ such that $x \in V_1$ and $||x-x_0||_1<\delta$ implies that 

<aside>

$$
||F(x)-F(x_0)||_2 <\epsilon
$$

</aside>

And F is said **continuous** on the set $E \subset V_1$ if it is continuous at each point $x\in E$

if F is continuous on $E \subset V_1$, then we write 

$$
F \in C(E)
$$

**Definition 3**: Suppose that $f: E\to \mathbb{R^n}$ is differentiable on E. Then $f \in C^1(E)$X if the derivative $Df: E \to L(\mathbb{R^n})$ is continuous on E. 

![Theorem 2](assets/images/notes/ode/Screenshot_2025-02-07_at_1.25.58_PM.png)

**Remark:** 

- for an open set E of $\mathbb{R^n}$, the higher order derivatives $D^kf(x_0)$  of function $f: E \to \mathbb{R^n}$  are defined in a similar way and it can be shown that $f\in C^k(E)$ iff its partial derivative $\frac{\partial^k f_i}{\partial x_{j1}...\partial x_{jk}}$ with 1… $j_k$ = 1….n, exists and are continuous on E.

## 2.2 Fundamental Existence-Uniqueness Theorem

<aside>

Picard’s classical method of successive approximations

</aside>

**Definition 1**: a solution of **differential equation $x(t)$**

**Definition 2**: Let $E$ be an open subset of $\mathbb{R^n}.$ A function $f: E \to \mathbb{R^n}$  is said to satisfy a ***Lipschitz condition*** on E if there is a positive constant K such that all $x,y \in E$,

$$
|f(x) - f(y)| \leq K|x-y|.
$$

The function $f(x)$ is **locally *Lipschitz*** on E **if ,for each point $x_0\in E,$ there is an $\epsilon$-neighborhood of $x_0$, $N(x_0) \subset E$, and a constant $K_0 >0$ such that for all $x,y \in N_{\epsilon}(x_0)$,

$$
|f(x)-f(y)| \leq K_0 |x-y|
$$

By $x_0 \in \mathbb{R^n}$, we mean an ***open ball*** of positive radius $\epsilon;$ i.e.: 

$$
N_{\epsilon}(x_0) = \{x\in\mathbb{R^n} | \space |x - x_0| < \epsilon\}
$$

**Lemma**: Let $E$ be an open subset of $\mathbb{R^n}.$ Then, if $f\in C^1(E)$, $f$ is ***locally Lipschitz*** on E

**Definition 3**: Let V be a normed linear space. Then a sequence $\{u_{k}\} \subset V$ is called ***Cauchy sequence*** if for all $\epsilon >0,$  there is an N such that $k,m \geq N$ implies that 

$$
||u_k-u_m|| \leq\epsilon
$$

The space V is called ***complete** if every Cauchy sequence* in V converges to an element in V

For $I = [-a,a]$,  $C(I)$ is a **complete normed linear space.**

**Theorem(The Fundamental Existence-Uniqueness Theorem):** Let $E$ be an  *open subset of $\mathbb{R^n}$*  containing $x_0$ and assume that $f \in C^1(E)$, then tehre exists an $a >0$ such that the *initial value problem:* 

$$
\dot{x} = f(x)\\ x(0) = x_0
$$

*has a unique solution $x(t)$ on the interval $[a,-a]$*

***Remark:***

- f(t) is differentiable, namely $x(t)$ is second differentiable
- With initial condition, we jave unique solution.
- PROOF:
    - first to construct the lipschitz condition from $f\in C^1(E)$
    - second, by integration to get the solution
    - then, prove the uniqueness

## 2.3 Dependence on Initial conditions and Parameters

<aside>

in IVP, initial question might depend on more than one parameter like 

$$
\dot{x}= f(x,\mu) \\x(0) =y
$$

in this way, we might ( $x_0 = u(0))$, the solution is $u(t,y,\mu)$

</aside>

**Lemma(Grownwall):** Suppose that $g(t)$ is a continuous real valued function taht satisfies $g(t) \geq 0$ and 

$$
g(t)\leq C+K \int_{0}^t g(s)ds 
$$

for all $t\in [0,a]$, where C and K are *positive constants.* It then follows that for all $t\in [0,a]$, 

$$
g(t) \leq C e^{Kt}
$$

**Theorem 1(Dependence on Initial Conditions):**  Let $E$ be an open subset of $\mathbb{R^n}$ containing $x_0$ and assume that $f\in C^1(E)$. Then there exists an $\alpha \geq 0$  and a $\delta \geq 0$ such that for all $y \in N_{\delta}(x_0)$, the initail value problem 

$$
\dot{x} = f(x) \\ x(0) = y
$$

has a  *unique solution $u(t,y)$ with $u\in C^1 (G)$ where $G = [-a,a] \times N_{\delta} \subset \mathbb{R^{n+1}}$; further more, for each $y \in N_{\delta}(x_0), u(t,y)$*  is a ***twice continuously differentiable function of*** $t$ fo***r $t\in [-a,a]$***

**Remarks:**

- conditions:
    - E is open subset
    - $f\in C^1(E)$ : **ensure the smootheness and stability**
    - initial value problem ( y is the neighbor)
- What theorem ensures:diff
    - IVP has ***unique*** solution
    - the solution function is differentiable with both ***t and y***
    - $u(t,y)$  is  ***twice continuously differentiable function***
- this theorem is to tell: small changes in initial condition will not cause erratic behavior

**Corollary:**  Under the hypothesis of the above theorem, 

$$
\Phi(t,y) = \frac{\partial u}{\partial y}(t,y)
$$

for $t \in [-a, a]$ and $y\in\mathbb{N_{\delta}}(x_0)$  * **if and only if**  $\Phi(t,y)$ is the fundamental matrix solution of* 

$$
\dot{\Phi} = Df[u(t,y)] \Phi \\ \Phi(0,y) = I
$$

for $t\in (-a,a)$ and $y \in \mathbb{N_{\delta}}(x_0)$

**Remark 1:** A similar proof shows that iif $f\in C^r(E)$ then the solution $u(t,y)$  of the initial value problem is in $C^r(G)$ where G is defined as in te\he above theorem. And if $f(x)$ is a real analytic function for $x\in E,$ then $u(t,y)$ is analytic in the interior of G

- analytic function: expanded as Tylor expansion: inifinitely differentiable?

**Remark 2: If $x_0$**  is an equilibrium point of (1), i.e, if $f(x_0) = 0$ so that $u(t,x_0) = x_0$ for all $t\in \mathbb{R}$, then 

$$
\Phi(t,x_0) = \frac{\partial u}{\partial x_0}(t,x_0)
$$

satisfies 

$$
\dot{\Phi} = Df(x_0)\Phi \\ \Phi(0,x_0) = I
$$

And according to the Fundamental Theorem for Linear Systems 

$$
\Phi(t,x_0) = e^{Df(x_0)t}
$$

**Remark3:** it follows from the continuity of the solution $u(t,y)$ of the initial value problem taht for each $t\in[-a,a]$, 

$$
\lim_{y\to x_0} u(t,y) = u(t,x_0)
$$

it follows form the inequality ([Grownwall’s Lemma](https://www.notion.so/MATH-119B-193e5ea8a15f8015ac36df0c7f62d852?pvs=21)) $|u(t,y_0+h)-u(t,y_0)|\leq |h| e^{K|t|}$ that this limit is uniform for all $t\in [-a,a]$

- uniformly convergence: we say taht $f(x_0)$ converges uniformly to $f(x)$  on a domain D if : $\sup_{x \in D} |f_n(x) - f(x)| \to 0 \quad \text{as } n \to \infty.$
    - the same speed applies to all a in domain D
    - this is to say a single N such that for all $n \geq N$ the function $f_n(x)$ stays uniformly close to $f(x)$ regardless of x

**Theorem 2(Dependence on Parameters)** Let E be an open subset of $\mathbb{R^{n+m}}$ containing the point $(x_0,\mu_0)$, where  $x_0 \in \mathbb{R^n}$ and $\mu_0 \in \mathbb{R^m}$ and assume that $f\in C^1(E)$. It then follows that there exists an $a > 0$ and a $\delta > 0$ such that for *all*  $y\in N_{\delta}(x_0)$ and $\mu \in N_{\delta}(\mu_0)$, teh initial value problem 

$$
\dot{x} = f(x,y) \\ x(0) = y
$$

has a unique solution $u(t,y,\mu)$ with $\mu \in C^1(G)$ where $G = [-a,a] \times N_{\delta}(x_0) \times N_{\delta}(\mu_0)$

## 2.4 The Maximal Interval of Existence

- In this section, we show that IVP **has a unique solution** x(t) defined on a maximal interval of existence $(a, \beta)$
- Furthermore, if $\beta < \infty$ an if the limit

$$
x_1 = \lim_{t \to\beta^-}x(t)
$$

exists then $x_1 \in \dot{E}$, the boundary of E.( $\dot{E} = \bar{E} \sim E$, where $\bar{E}$ denotes the clsure of )

- if teh above limit exists and $x_1 \in E$, then $\beta = \infty$ , $f(x_1) =0$ and x_1 is an equilibrium point of IVP

**Lemma:** Let E be an open subset of $\mathbb{R^{n}}$ containing $x_0$ and suppose $f\in C^1(E)$. Let $u_1(t)$ and   $u_2(t)$  be solutions of the initial value problem(1) on the intervals $I_1$ and $I_2$. Then $0\in I_1 \cap I_2$ and if $I$  is any open interval containing 0 and contained in $I_1 \cap I_2$, it follows that $u_1(t) = u_2(t)$ for all $t\in I$

- Uniqueness  $u_1 = u_2$ on the overlap interval

**Theorem 1**: Let E be open susbset of $\mathbb{R^n}$. and assume that $f\in C^1(E)$. Then for each point $x_0 \in E$, there is a maximal interval $J$ on which the initial value problem has a unique solution $x(t).$  If the initial value problem has a solution $y(t)$ on an interval $I$ then $I\cap J$ and $y(t) = x(t)$ for all $t\in I.$ Furthermore, the maximal interval J is open: $J = (a, \beta)$

**Definition:** The interval $(a,\beta)$ in Theorem 1 is called the ***maximal interval of existence*** of teh solution $x(t)$  of the initial value problem (1) or simply the maximal interval of existence of the initial value problem. 

**Theorem 2:** Let $E$  be an open subset of $\mathbb{R^n}$ containing $x_0$, let $f\in C^1(E),$ and let $(a,\beta)$ be the maximal interval of existence of the solution $x(t)$ of the initial value problem. Assume that $\beta < \infty$. Then given any compact set $K \subset E$, there exist a $t\in (a, \beta)$ such that $x(t) \notin K$

Intuition: 

1. this theorem describes the behavior of solutions to an initial value problem when the maximal interval of existence $(a,\beta)$ is finite.
2. It essentially states that if the solution exists only up to a finite time $\beta$, then as t approaches $\beta$, the solution $x(t)$ must "leave" any compact subset $K$ of $E$

**Theorem 3**: Let E be an open subset of $\mathbb{R^n}$  containing $x_0$, let $f\in C^1 (E)$, and let $[0,\beta)$ be the right maximal interval of existence of teh solution $x(t)$ of the initial value problem. Assume that $\beta < \infty$. Then given any compact set $K \subset E$, there exists a $t \in (0,\beta)$ such that $x(t) \notin K$

**Theorem 4**: Let E be an open subset of $\mathbb{R^n}$ containing $x_0$ and let $f \in C^1(E)$. Suppose that initial value problem has a solution $x(t,x_0)$  defined on a closed interval $[a,b]$. Then there exists a $\delta >0$ and a positive constant $K$ such that for all  $y \in N_{\delta}(x_0)$ the initial value problem:

$$
\dot{x} = f(x) \\ x(0) = y
$$

has a  *unique solution* $x(t,y)$ defined on $[a,b]$ which satisfies $|x(t,y) - x(t,x_0| \leq |y-x_0|e^{K|t|}$ and 

$$
\lim_{y\to x_0} x(t,y) = x(t,x_0)
$$

uniformly for all $t \in [a,b]$

Remark:

- the difference will grow exponentially with t
- uniform: convergen happened at the same rated

## 2.5 The Flow defined by a Differential Equation

[The flow $\phi_t$](https://www.notion.so/MATH-119B-193e5ea8a15f8015ac36df0c7f62d852?pvs=21) of the non-linear system 

$$
  \dot{x} = f(x) \tag{1}
$$

we denote the **maximal interval** of existence $(\alpha, \beta)$ of the solution $\phi(t,x_0)$  of the initial value probelm 

$$
\tag{2}\dot{x} = f(x) \\ x(0) = x_0 
$$

by $I(x_0)$ since the endpoint $\alpha$ and $\beta$ of the maximal interval generally depend on $x_0$

**Definition 1**: Let $E$ be an open subset of $\mathbb{R^n}$ and let $f\in C^1(E)$. For $x_0 \in E$, let $\phi(t,x_0)$ be the solution of the initial value problem [(2)](https://www.notion.so/MATH-119B-193e5ea8a15f8015ac36df0c7f62d852?pvs=21) defined on its maximal interval of existence $I(x_0)$. Then for $t\in I(x_0)$, the set of mapping $\phi_t$ defined by 

$$
\phi_t(x_0) = \phi(t,x_0)
$$

is called the  *flow of the differential equation (1)*   or the flow defined by the differential equation (1); $\phi_t$ is also referred to as *the flow of the vector field*  $f(x)$

**Remark:**

- we can think of it as a solution curve or *trajectory of the system* if think initial point $x_0$ is fixed:  $\phi(. , x_0): I(x_0) \to E$
- if we think of the point $x_0$ as varying throught $K\subset E$, then the flow of the differential equation(1) $\phi_t: K\to E$ can be view as teh motion of all teh points in the set K.
- trajectory $\phi_t$: motion of an individual particle in the fluid

Example 1 : See notability

<aside>

NTS: $\phi_t$ for non-linear system also satisfy [three properties](https://www.notion.so/MATH-119B-193e5ea8a15f8015ac36df0c7f62d852?pvs=21): 

1. $\phi_0(x) = x$
2. $\phi_s(\phi_t(x)) = \phi_{s+t}(x)$
3. $\phi_{-t}(\phi_t(x)) = \phi_t(\phi_{-t}) = x \hspace{1cm} for  \space t\in \mathbb{R}$
</aside>

Define: the set  $\Omega \subset \mathbb{R}\times E$

$$
\Omega = \{(t,x_0) \in \mathbb{R} \times E | t\in I(x_0)\}
$$

**Theorem 1(Global smoothness of the solution):** Let $E$ be an open subset of   $\mathbb{R^n}$ and let $f\in C^1(E) .$ Then $\Omega$   *is an open subset of $\mathbb{R} \times E$ and the solution $\phi \in C^1(\Omega)$*

![concept](assets/images/notes/ode/Screenshot_2025-02-09_at_4.12.01_PM.png)

- NTS:  $\Omega$ is an open subset and then for all $z\in\Omega, \exist \delta>0,\space N_{\delta}\subseteq\Omega$

Remark:

1.  [Theorem 1](https://www.notion.so/MATH-119B-193e5ea8a15f8015ac36df0c7f62d852?pvs=21) can be generalized to show that if $f\in C^r(E)$ with $r \geq 1$, then $\phi \in C^r(\Omega)$ and 
2. that if f is analytic in E, then $\phi$ is analytic in $\Omega$
    - the global smoothness of solution depends on the smoothness of the vector field $f$

**Theorem 2:** Let $E$ be an open subset of   $\mathbb{R^n}$ and let $f\in C^1(E) .$ Then for all $x_0 \in E,$ if $t \in I(x_0)$ and $s\in I(\phi_t(x_0))$, it fllows that $s+t \in I(x_0)$ and 

$$
\phi_{s+t}(x_0) = \phi_s(\phi_t(x_0))
$$

Remark: In other words, if we have well defined solution $\phi_t(x_0)$ that evolves a point $x_0$ in time, this thm2 states that if we first move teh particle at $x_0$ by time t (we get position $\phi_t(x_0$) then move this resulting point by an additional time s, $\phi_s(\phi_t(x_0))$, then we get teh same result as moving $x_0$ directly by total time.

**Theorem 3**: Under the hypotheses of [Theorem 1](https://www.notion.so/MATH119B-193e5ea8a15f803ca44afc6ffe5a8262?pvs=21), if $(t,x_0) \in \Omega$ then  *there exists a neighborhood U of $x_0,$  such that ${t} \times U \subset \Omega$. It then follows taht the set $V=\phi_t(U)$ is open in E and that* 

$$
\phi_{-t}(\phi_t(x)) = x \quad for \space all \space x\in U
$$

and 

$$
\phi_{-t}(\phi_t(y)) = y \quad for \space all \space y\in V
$$

**Definition 2**: Let E be an open subset of $\mathbb{R^n}$, let $f\in C(E)$, and let $\phi_t: E\to E$ be the flow of the differential equation (1) defined for all $t \in R$. 

- Then a set $S \subset E$ is called ***invariant*** with respect to the flow $\phi_t$ if $\phi_t(S) \subset S$ for all $t  \in R$
- and $S$ is called  ***positively(or negatively) invariant with respect to the flow $\phi_t$***  if $\phi_t(S) \subset S$ for all $t \ge 0(\space or \space  t \le0)$

## 2.6 linearization

**Definition 1**: A point $x_0 \in \mathbb{R^n}$ is called an ***equilibrium point*** or ***critical point*** of $\dot{x} = f(x)$ if $f(x_0) = 0$. An equilibrium point is called a ***hyperbolic equilibrium poin**t* $x_0$ if none of the eigenvalues of the matrix $Df(x_0)$ have zero real part. The linear system $\dot{x} = Ax$ with the matrix $A = Df(x_0)$ is called the ***linearization*** of  $\dot{x} = f(x)$ at $x_0$

**Remark 1:**

- because of Taylor Theorem,

$$
f(x) = Df(0) + \frac{1}{2}D^2f(0)(x,x)+...
$$

It follows that $Df(x_0)$ is a good first approximation to the nonlinear function $f(x)$ near $x =0$

- the behavior of non linear system new x_0 will be approximated by teh behavior of its linearization

**Remark 2:**

- if $x_0$  is an equilibrium point and $\phi_t: E \to \mathbb{R^n}$ is the flow of the differnetial equation, then $\phi_t(x_0) = x_0$ for all $t\in R$
- $x_0$  is called a fixed point of the flow $\phi_t$
- it is also called a  ***zero, a critical point, or a singular point of the vector field $f: E\to R^n$***

**Definition 2:** 

- sink: An equilibrium $x_0$  of $\dot{x} = f(x)$ is called a sink if all of the eignvalues of teh matrix $Df(x_0)$  have negative real part
- source: if all of the eigenvalues of the matrix $Df(x_0)$  have positive real part
- saddle: if it is hyperbolic equilibrium point and $Df(x_0)$  has at least one eigenvalue with a positive real part and at least one with a negative real part.

In secion 2.8, we can see if $x_0$ is a hyperbolic equilibrium point of (1) then the local behavior of the **non linear system** is topologically equivalent to the local behavior of the **linear system(2).** 

- these is a continuous one to one map of a neighborhood of $x_0$ onto an open set U containing the origin, $H: N_{\epsilon}(x_0) \to U$
- transform non lienar to linear system
- H preserves the direction along the trajectories

## 2.7 The Stable Manifold Theorem

1. It shows that near a ***hyperbolic equilibrium point*** $\vec{x_0}$, the non linear system $\vec{x} = \vec{f}(\vec{x})$ has **stable and unstable manifold $S$  and U tangent** at $x_0$ to the stable and unstable subspace $E^S$ and $E^U$ of the linearized system 
    
    $$
    \vec{x} = A \vec{x}
    $$
    
    where $A = D\vec{f}(\vec{x})$
    
2. Furthermore, $S$ and U have the ***same dimension*** as $E^S$ and $E^U$
3. And if $\phi_t$ is the flow of the nonlinear system, then $S$ and $U$ are positively and negatievly invariant under $\phi_t$ respectively and satify 

$$
\lim_{t \to \infty}\phi_t(c) = \vec{x_0} \quad for \space all \space c\in S
$$

$$
\lim_{t\to -\infty} \phi_t(c) = \vec{x_0} \quad for \space all \space c\in U
$$

**Defintion 1**: Let X be a matrix space and let A and B be subsets of X. A homeomorphism of A onto B is a continuous one-to-one map of A onto B, $h:A\to B$, such that  $h^{-1}:B\to A$ is continuous. The sets A and B are called **homeomorphic or topologically equivalent** if there is a homeomorphism of A onto B. IF we wish to emphasize that h maps A onto B, we write $h:A \cong B$

Remark:

- the definition of homeomorphism:
    - continuous
    - one to one
    - onto
    - inverse function

**Definition 2**: An ***n-dimentional differentiable manifold*** $M$ (or a manifold f class $C^k$) is a ***connected metric*** space with an open covering $\{U_a\}$i.e. $M = \cup_a U_a$, such that 

1. for all $a,U_a$ is a homeomorphism to the ***open unit ball in*** $R^n$,$B = \{x\in R^n| |x<1|\}$,i.e. for all $\alpha$  there exists a homeomorphism of $U_a$ onto B,  $h_a: U_a\to B$, and
2. if $U_a\cap U_{\beta} \neq \empty$, and $h_a: U_a \to B$, $h_{\beta}: U_{\beta} \to B$ are homeomorphisms, then $h_a(U_a \cap U_{\beta})$ and $h_{\beta}(U_a \cap U_{\beta})$ are subsets of $R^n$ and the map  

$$
h = h_{\alpha} \circ h_{\beta}^{-1}: h_{\beta}\bigl(U_{\alpha} \cap U_{\beta}\bigr) \;\longrightarrow\; 
  h_{\alpha}\bigl(U_{\alpha} \cap U_{\beta}\bigr) \\
$$

is differnetiable (or of class $C^k$) and for all $x\in h_{\beta}(U_a \cap U_{\beta})$, the Jacobian determinant det $Dh(x) \neq 0$. The manifold M is said to be **analytic** if the maps $h = h_{\alpha} \circ h_{\beta}^{-1}$ are **analytic**

![Screenshot 2025-02-13 at 2.30.38 AM.png](assets/images/notes/ode/Screenshot_2025-02-13_at_2.30.38_AM.png)

**Theorem(The Stable Manifold Theorem)**: Let $E$ be an open subset of $R^n$ containing the origin, let  $f \in C^1(E)$,a dn let $\phi_t$ be the flow of the non-linear system. Suppose that $f(0) = 0,$ and that **$Df(0)$** has $k$ eigenvalues with negative real part and $n-k$ eigenvalues with positive real part. Then there exists a  $k- dimensional$ differentiable  manifold S tangent to the stable subspace $E^S$ of the linear system(2) at 0 such that for all $t \geq 0, \phi_t(S) \subset S$ and for $all \space x_0 \in S$. 

$$
\lim_{t \to \infty} \phi_t(x_0) = 0;
$$

and there exists an $n-k$ $dimensional$  differnetiable manifold $U$ tangent to the unstable subspace $E^u$ of (2) at 0 such that for $all \space t \leq 0, \phi_t(U) \subset U$ and for $all \space x_0 \in U,$

$$
\lim_{t \to -\infty}\phi_t(x_0) = 0.
$$

**Remark:**

Statement of the tehoreom:

*Let:*

- $E$ be an open subset of $R^n$ containing the origin.
- $f \in C^1(E)$, meaning f is continuously differentiable.
- $\phi_t$ be the **flow** generated by the nonlinear system x˙=f(x).

*We assume:*

- $f(0)=0,$ meaning the origin is an **equilibrium point**.
- The **Jacobian matrix** Df(0) has:
    
    $Df(0)$
    
    - $k$ eigenvalues with **negative real part**.
    - $n−k$  eigenvalues with **positive real part**.

*Conclusion:*

1. a stable manifold $S$
    1. a  $k- dimensional$ differentiable  manifold S 
    2. tangent to the stable subspace $E^S$ of the linear system(2) at 0 
    3.  for all $t \geq 0, \phi_t(S) \subset S$ and for $all \space x_0 \in S$ and approach teh origin as $t \to \infty$
2. an unstable manifold $U$
    1. an $n-k$ $dimensional$  differnetiable manifold $U$
    2.  tangent to the unstable subspace $E^u$ of (2) at 0
    3.  for $all \space t \leq 0, \phi_t(U) \subset U$ ,and for $all \space x_0 \in U,$ 
    
    $$
    \lim_{t \to -\infty}\phi_t(x_0) = 0.
    $$
    

**Remark #1**: $\vec{f} \space in \space C^1(E)$  and $\vec{f}(0) = \vec{0}$ , then the system  $\dot{\vec{x}} = \vec{f(x)}$ can be written as 

$$
\dot{\vec{x}} = A\vec{x} + \vec{F}\vec{x}
$$

where $A = D\vec{f(0)}$ and  $\vec{F(x)} = \vec{f(x)} -A\vec{x}$

Then, $\vec{F} \space in \space C^1(E)$  and  $\vec{F}(0) = \vec{0}$ , and $D\vec{f(0)} = \vec{0}$, and $\vec{F}$ is Lipschitz continuousi.e. for all $\epsilon > 0, \exists \delta >0, s.t.$  for all $x,y \in N_{\delta}(0),$ we ahev 

$$
|\vec{F(x)} - \vec{F(y)}| \leq \epsilon|\vec{x} - \vec{y}|
$$

**Remark#2: Jordan format of matrix**

There eist an $n \times n$ invertible matrix C s.t. 

$$
B = C^{-1}AC = \begin{bmatrix}
P & 0 \\
0 & Q
\end{bmatrix}
$$

where the eigenvalues $\lambda_1, \lambda_2,..., \lambda_k$ of $P_{k \times k}$ have  **negative real part**

and the eigenvalues $\lambda_{k+1}...\lambda_{n}$ of $Q_{(n-k)\times (n-k)}$ have positive real part

Wec an choose $\alpha > 0$ sufficiently small that for $j = 1,2,..., k,$ 

$$
Re(\lambda_{j}) < -\alpha < 0
$$

Remark#3: 

<aside>

norm of matrix: 

</aside>

<aside>

norm of vector

</aside>

# Chapter 4

Non-linear systems of differential equations

$$
\dot{x} = f(x)
$$

If the qualitative behavior remains the same for all near by vector fields, then the system or the vector field is said to be **structurally stable**

- Small modifications to f(x) do not change the number or stability of equilibrium points.
- If a system is **not** structurally stable, it belongs to the **bifurcation set** in $C^1(E)$, meaning it undergoes bifurcations.

historical 

- **Andronov & Pontryagin (1937)** developed the concept of structural stability.
- **Peixoto’s Theorem** (for 2D systems) fully characterizes structurally stable vector fields.

Sable manifold theorem

## 4.1 structural stability and Peixoto’s theorem

<aside>

topologically equivalent:

### **Definition:**

Two vector fields $f(x)$ and $g(x)$ are **topologically equivalent** if there exists a **homeomorphism** $h:R^n→R^n:$  such that:

- $h$ maps trajectories of $f(x$) to trajectories of  $g(x)$  while preserving the direction of time.
- $h$ is **continuous** and has a **continuous inverse**.

This means that solutions of $\dot{x} = f(x)$ can be smoothly transformed into solutions of  $\dot{x} = g(x)$ without changing their fundamental structure.

</aside>

### **1. Structural Stability**

A **structurally stable vector field** (or dynamical system) is one where **small perturbations do not change the qualitative behavior** of the system. This means that:

- For any vector field $g$ that is close to $f$, the two vector fields are **topologically equivalent** (i.e., they have the same phase portrait up to continuous transformations).
- **Topological equivalence** means that the behavior of trajectories (e.g., equilibrium points, periodic orbits, and their stability) remains the same.

This concept was introduced by **Andronov and Pontryagin (1937)** and is fundamental in the study of dynamical systems.

![Screenshot 2025-03-09 at 12.38.32 PM.png](assets/images/notes/ode/Screenshot_2025-03-09_at_12.38.32_PM.png)

$C^1$ norm: This norm measures the **magnitutes** of both $f(x)$ and its first derivative, ensuring that both the function value and its variation are considered when comparing two vector fields

**Properties:**

- The space of functions within $C^1$ is a Banach space(complete norm space)
- This completeness ensures that limits of Cauchy sequences (functions getting arbitrarily close) exist within the space.
- **is used to define distances** between vector fields and helps in proving structural stability results.