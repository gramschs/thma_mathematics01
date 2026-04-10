---
authors:
  - name: Simone Gramsch
---

# 8.3 Optimization Problems

Curve sketching organises everything we know about a function that is already
given to us. In engineering the more common situation is different: we have
a design goal and a set of constraints, and we must find the parameter values
that achieve the best outcome. The function to be optimised is not handed to
us but must be constructed from the problem statement. Setting up that
construction, reducing it to a single-variable problem, and then applying the
tools of section 8.1 is the full workflow of engineering optimisation.

```{admonition} Learning goals
:class: attention
* [ ] You can translate a verbal engineering problem into a mathematical **objective function** and identify the relevant **constraints**.
* [ ] You can use the constraints to reduce the objective function to a function of a single variable.
* [ ] You can solve an optimization problem by finding the critical points of the reduced objective function and classifying them using the second derivative test.
* [ ] You can verify that a solution is physically meaningful and interpret it in the context of the original engineering problem.
```

## What is the design problem?

A water utility requires a closed cylindrical storage tank that holds exactly
$V_0 = 16\pi~\text{m}^3$ of water, approximately 50 cubic metres, a typical
capacity for a small supply facility. The tank has a circular top and bottom,
each of radius $r$, and a cylindrical lateral wall of height $h$. The total
surface area is

\begin{equation*}
A = 2\pi r^2 + 2\pi r h,
\end{equation*}

where $2\pi r^2$ is the combined area of the two circular caps and $2\pi r h$
is the lateral area. The cost of construction is proportional to the total
surface area, so the utility wants to minimise $A$ subject to the volume
constraint $\pi r^2 h = V_0$.

*Why should a minimum exist at all?* If $r$ is very small the tank must be
very tall to contain the required volume, and the lateral wall area $2\pi r h$
grows without bound as $r \to 0^+$. If $r$ is very large the tank is a flat
disc and the area of the two circular caps dominates. Somewhere between these
extremes there is an optimal proportion.

## How do we reduce the problem to a single variable?

The objective function $A$ depends on two variables, $r$ and $h$. The volume
constraint links them:

\begin{equation*}
\pi r^2 h = 16\pi \implies h = \frac{16}{r^2}.
\end{equation*}

Substituting into $A$:

\begin{equation*}
A(r) = 2\pi r^2 + 2\pi r \cdot \frac{16}{r^2}
= 2\pi r^2 + \frac{32\pi}{r}, \quad r > 0.
\end{equation*}

The problem is now one-dimensional: find the value of $r > 0$ that minimises
$A(r)$.

## What are the optimal dimensions?

We differentiate $A(r)$ using the power rule:

\begin{equation*}
A'(r) = 4\pi r - \frac{32\pi}{r^2} = \frac{4\pi(r^3 - 8)}{r^2}.
\end{equation*}

Setting $A'(r) = 0$ requires $r^3 = 8$, so $r = 2~\text{m}$. This is the
only critical point of $A$ on $(0, \infty)$.

We classify it with the second derivative:

\begin{equation*}
A''(r) = 4\pi + \frac{64\pi}{r^3}.
\end{equation*}

Both terms are positive for every $r > 0$, so $A''(r) > 0$ throughout, and
in particular $A''(2) > 0$: confirmed local minimum. Since $A(r) \to +\infty$
as $r \to 0^+$ and as $r \to +\infty$, and the only critical point is a
minimum, this is also the global minimum on $(0, \infty)$.

The optimal height follows from the constraint:

\begin{equation*}
h = \frac{16}{r^2} = \frac{16}{4} = 4~\text{m}.
\end{equation*}

## How do we verify and interpret the solution?

We first check the volume: $\pi r^2 h = \pi \cdot 4 \cdot 4 = 16\pi~\text{m}^3$
✓. The minimum surface area is

\begin{equation*}
A(2) = 2\pi(4) + \frac{32\pi}{2} = 8\pi + 16\pi = 24\pi \approx 75.4~\text{m}^2.
\end{equation*}

The most striking feature of the result is the relationship between height and
radius: $h = 4~\text{m} = 2 \times 2~\text{m} = 2r$. The optimal height equals
the diameter. This is a universal result: for any fixed volume, the closed
cylinder with minimum surface area satisfies $h = 2r$, regardless of the
value of $V_0$.

We can confirm that the endpoint behaviour supports this conclusion.
The surface area at two alternative radii is:

| Radius $r$ [m] | Height $h$ [m] | $A(r)$ [m²] |
| --- | --- | --- |
| $1$ | $16$ | $\approx 107.5$ |
| $2$ | $4$ | $24\pi \approx 75.4$ (optimal) |
| $4$ | $1$ | $\approx 108.9$ |

A tank that is too narrow or too flat both require substantially more material
than the optimal proportion. The minimum is broad rather than sharp: halving
or doubling the optimal radius increases the area by roughly 40 percent, which
means the design is relatively tolerant of small deviations from the optimum.

<!--
  SVELTE APP: "Cylindrical tank optimiser"

  LEFT PANEL: a 3D schematic of the cylinder, updating live as r changes.
  The cylinder is drawn with radius r and height h = 16/r², labelled with
  both dimensions. When r = 2 the cylinder has a clearly proportional look
  (h = 2r); for other values the shape is visibly distorted.

  RIGHT PANEL: the graph of A(r) = 2πr² + 32π/r on [0.5, 6].
    A movable point at (r, A(r)) with a slider for r, default r = 2.
    A dashed vertical line and horizontal annotation at r = 2 labelled
    "optimal: r = 2 m, A = 24π".
    The three rows of the comparison table above shown as dots on the curve.

  Two info tiles:
    - "A(r)" in m², updating with the slider.
    - "h = 16/r²" in m, updating with the slider.

  Purpose: students see the cylinder change shape as they drag r, and watch
  the total area cost update. The minimum is clearly visible on the curve,
  and the shape of the optimal cylinder (h = 2r) is immediately recognisable.
-->

## Where do optimization problems appear in engineering?

The cylindrical tank illustrates the structure of every optimisation problem:
an objective, at least one constraint, a reduction to a single variable, and a
derivative calculation to locate the optimum. The same workflow applies across
engineering disciplines.

In hydraulic engineering, the cross-section of an open irrigation channel is
designed to maximise the flow rate for a given amount of lining material. A
rectangular channel of fixed perimeter has an optimal width-to-depth ratio,
found by the same method as the cylinder, and the result (width equals twice
the depth) is a practical guideline used throughout the design of drainage
networks.

In manufacturing, the optimal production batch size balances the fixed cost of
setting up a machine run (which favours large batches) against the cost of
holding inventory (which favours small batches). The total cost function, a
sum of a term proportional to batch size and a term inversely proportional to
it, has exactly the algebraic structure of $A(r)$, and the critical point is
the familiar economic order quantity formula.

In structural engineering, the cross-section of a beam is sized to carry a
given bending moment with minimum weight. The optimal distribution of material
within the cross-section, keeping the flanges as far from the neutral axis as
the geometry allows, is the design principle behind I-beams and H-sections.
Each of these applications begins with a verbal description and ends with
a derivative set to zero.

## Summary and outlook

We have solved a concrete engineering optimisation problem: identifying the
objective and constraint, reducing to a single-variable function $A(r)$,
locating the critical point at $r = 2~\text{m}$, classifying it as a global
minimum, and verifying the solution. The optimal cylindrical tank has
$r = 2~\text{m}$ and $h = 4~\text{m}$, satisfying the universal relation
$h = 2r$, with a minimum surface area of $24\pi~\text{m}^2$.

The methods developed throughout this chapter have relied on the first and
second derivatives to describe functions locally and to locate extrema. In
the final section we take a wider view and ask: how well can a polynomial
approximate an arbitrary function, using not just the first two derivatives
but all the higher-order derivatives introduced in chapter 7? The answer
unifies the tangent line approximation of chapter 5 with the higher-order
machinery of chapter 7 into a single, powerful construction.
