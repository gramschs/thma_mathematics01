---
authors:
  - name: Simone Gramsch
---

# 5.5 The Tangent Line

In section 5.2 we described the tangent line geometrically as the limiting
position of the secant line as the step size shrinks to zero, and we identified
its slope as the differential quotient $f'(x_0)$. In section 5.4 we established
that this tangent exists precisely at the points where $f$ is differentiable.
We now put these two facts together and write down the equation of the tangent
line explicitly. The resulting formula is more than a geometric description of
a straight line: it is the simplest possible approximation of a curved function
in the neighbourhood of a point, and it underpins a wide range of engineering
calculations.

```{admonition} Learning goals
:class: attention
* [ ] You can write down the equation of the **tangent line** to the graph
  of $f$ at a point $(x_0, f(x_0))$:
  \begin{equation*}
  t(x) = f(x_0) + f'(x_0)\,(x - x_0).
  \end{equation*}
* [ ] You understand the tangent line as a **linear approximation** of the
  function in a neighbourhood of $x_0$.
* [ ] You can compute the tangent line for a given function and a given point,
  and interpret its slope and intercept in the context of the application.
```

## What is the equation of the tangent line?

A straight line is completely determined by one point it passes through and
its slope. We know both: the tangent at $x_0$ passes through the point
$(x_0,\, f(x_0))$ on the graph, and its slope is $f'(x_0)$. From the
point-slope form of a line we obtain immediately:

\begin{equation*}
t(x) = f(x_0) + f'(x_0)\,(x - x_0).
\end{equation*}

```{admonition} What is ... the tangent line?
:class: note
Let $f$ be differentiable at $x_0$. The **tangent line** to the graph of $f$
at the point $(x_0, f(x_0))$ is the straight line

\begin{equation*}
t(x) = f(x_0) + f'(x_0)\,(x - x_0).
\end{equation*}

Its slope is $f'(x_0)$ and it passes through the point $(x_0, f(x_0))$.
```

We can verify the formula immediately: substituting $x = x_0$ gives
$t(x_0) = f(x_0)$, confirming that the tangent line and the curve share the
same point at $x_0$. Substituting $x = x_0 + h$ and dividing the rise
$t(x_0 + h) - t(x_0) = f'(x_0) \cdot h$ by the run $h$ gives back $f'(x_0)$,
confirming the slope.

Note the connection to the straight rail of section 3.1. The height function
of that rail was $f(x) = -\tfrac{1}{4}\,x + 6$, a linear function with slope
$-\tfrac{1}{4}$ everywhere. The tangent line to a straight rail at any point
is the rail itself — a linear function is its own tangent, and its derivative
is the constant slope.

## How do we find the tangent line at a given point on the track?

For our parabolic track $f(x) = 0.02\,x^2 - 0.6\,x + 6$ with derivative
$f'(x) = 0.04\,x - 0.6$, we compute the tangent at three positions of
interest.

At $x_0 = 5~\text{cm}$, near the starting block, the function value and slope
are $f(5) = 3.5$ and $f'(5) = -0.4$. The tangent line is

\begin{equation*}
t(x) = 3.5 + (-0.4)\,(x - 5) = -0.4\,x + 5.5.
\end{equation*}

At $x_0 = 15~\text{cm}$, the vertex, we have $f(15) = 1.5$ and $f'(15) = 0$.
The tangent line is

\begin{equation*}
t(x) = 1.5 + 0 \cdot (x - 15) = 1.5,
\end{equation*}

a horizontal line. At the lowest point of the track the rail is momentarily
flat, exactly as expected.

At $x_0 = 25~\text{cm}$, on the rising right half, we have $f(25) = 3.5$ and
$f'(25) = 0.4$. The tangent line is

\begin{equation*}
t(x) = 3.5 + 0.4\,(x - 25) = 0.4\,x - 6.5.
\end{equation*}

The three tangent lines reflect the symmetry of the parabola about $x = 15$:
the slopes at $x = 5$ and $x = 25$ are equal in magnitude and opposite in
sign, and the function values are identical at both points. The tangent at the
vertex is horizontal, confirming the interpretation of section 5.3 that $f'(x)$
changes sign at the lowest point.

## How well does the tangent line approximate the curve?

The tangent line and the curve agree at $x_0$ and have the same slope there.
For $x$ close to $x_0$, the tangent line therefore provides an approximation
of the function value:

\begin{equation*}
f(x) \approx t(x) = f(x_0) + f'(x_0)\,(x - x_0).
\end{equation*}

*How accurate is this approximation?* We can answer this concretely for the
marble track. Using the tangent at $x_0 = 5$ to approximate the height at
nearby positions:

| $\Delta x = x - x_0$ [cm] | $t(5 + \Delta x)$ [cm] | $f(5 + \Delta x)$ [cm] | Error [cm] |
| --- | --- | --- | --- |
| $0.3$ | $3.38$ | $3.3818$ | $0.0018$ |
| $1.0$ | $3.10$ | $3.12$ | $0.02$ |
| $2.0$ | $2.70$ | $2.78$ | $0.08$ |

The errors $0.0018$, $0.02$, and $0.08$ are exactly $0.02 \cdot (\Delta x)^2$.
When $\Delta x$ doubles, the error quadruples. This is characteristic of linear
approximation: the error grows with the square of the step, while the step
itself grows only linearly. For small $\Delta x$ the quadratic error is
negligible, and the tangent line is an excellent description of the curve. For
large $\Delta x$ the error accumulates quickly.

If we zoom in on the graph around $x_0 = 5$, magnifying the region more and
more, the parabola begins to look straight. In the limit of infinite
magnification, the parabola and its tangent line are indistinguishable. This
is the geometric content of differentiability: a differentiable function looks
linear at every scale small enough. The approximation

\begin{equation*}
f(x_0 + \Delta x) \approx f(x_0) + f'(x_0)\,\Delta x
\end{equation*}

is called the **linear approximation** or **linearisation** of $f$ at $x_0$.

```{raw} html
<!--
  SVELTE APP: "Tangent line and linear approximation"

  MAIN VIEW (full domain [0, 30]):
    - The parabola f(x) = 0.02x² - 0.6x + 6 in dark blue.
    - The tangent line t(x) at x0 in green, extending across the full plot.
    - A filled dot at (x0, f(x0)) in orange.
    - A slider for x0 across [0, 30], default 5.
    - A second slider for a query point x1, shown as a second dot
      (red) at (x1, f(x1)), with a dashed vertical line connecting
      (x1, f(x1)) to (x1, t(x1)) and labelled "error".

  ZOOM INSET (bottom-right corner of the main view):
    - A magnified view of the region [x0 - w, x0 + w] in both x and f,
      where w = 2 by default.
    - A slider labelled "zoom" reduces w from 2 down to 0.05.
    - As w decreases, the parabola segment inside the window straightens
      and becomes visually indistinguishable from the tangent line,
      illustrating the "locally linear" character of differentiable functions.

  Info tiles below the main view:
    - "x0" showing the base point.
    - "f(x0)" showing the function value.
    - "f'(x0)" showing the slope 0.04·x0 - 0.6.
    - "t(x) =" showing the tangent line formula as a string,
      e.g. "-0.40x + 5.50".
    - "Approximation error at x1" showing |f(x1) - t(x1)| to 4 decimal
      places, colored green when below 0.05 and red above.

  Preset buttons at x0 = 5, 15, 25 reproduce the three cases computed
  in the text.

  Purpose: the zoom feature is the central pedagogical element. Students
  see that "differentiable means locally linear" is not a metaphor but a
  visual fact. The error tile at x1 reinforces that the approximation
  degrades quadratically as x1 moves away from x0.
-->
```

## Where does linear approximation appear in engineering?

The tangent line formula is one of the most frequently applied tools in
engineering mathematics. It appears wherever a nonlinear relationship must be
handled with linear methods.

In sensitivity analysis, we ask: if an input to a system changes by a
small amount $\Delta x$, by how much does the output change? The answer,
to first order, is $f'(x_0) \cdot \Delta x$. This is the tangent line
approximation applied to the input-output relationship of the system. A
tolerance of $\pm 0.1~\text{mm}$ on a machined part, for example, propagates
through the design formula via the derivative to give the resulting tolerance
on the final dimension.

In control engineering, the dynamics of a system are often described by
nonlinear differential equations. Near a steady operating point $x_0$, the
nonlinear term $f(x)$ is replaced by its linearisation $f(x_0) + f'(x_0)(x - x_0)$.
This produces a linear system that can be analysed with the full toolkit of
linear control theory. The quality of the control design depends on how well
the linearisation captures the true nonlinear behaviour, which in turn depends
on how far the system strays from $x_0$ during operation.

Both applications rest on the same mathematical fact: for small deviations
from a reference point, the error of the linear approximation is quadratic in
the deviation, and can therefore be made arbitrarily small by staying close to
the reference point. In a later chapter we will develop more accurate
polynomial approximations that reduce the error further by adding quadratic
and higher-order terms. These are the Taylor polynomials, and they generalise
the tangent line formula in a natural direction.

## Summary and outlook

This section completes chapter 5. Starting from the difference quotient as
the average rate of change over a finite interval, we passed through the limit
to reach the differential quotient as the instantaneous rate of change at a
single point. Varying the base point across the domain produced the derivative
function, a new function that encodes the slope of the original curve
everywhere. The concept of differentiability identified the points where this
construction succeeds: exactly those where the curve has a unique, finite
tangent direction and no jump, corner, cusp, or vertical tangent is present.
The tangent line, the centrepiece of this final section, gives the limiting
secant a concrete equation and simultaneously the best linear approximation of
the function near the chosen point.

All five concepts, difference quotient, differential quotient, derivative
function, differentiability, and tangent line, are built on a single
mathematical operation: the limit of the ratio $\Delta f / \Delta x$ as
$\Delta x \to 0$. In chapter 5 we have computed this limit from scratch for
polynomial functions. This is correct and rigorous, but it is also slow.
The next chapter introduces differentiation rules that bypass the limit
calculation entirely, letting us find the derivative of sums, products,
quotients, and compositions of functions in a few steps. With those rules
the full power of differential calculus becomes practical.
