---
authors:
  - name: Simone Gramsch
---

# 5.2 The Differential Quotient

In the previous section we computed the difference quotient for the parabolic
marble track at $x_0 = 5~\text{cm}$ with three decreasing step sizes and
obtained the values $-0.1$, $-0.3$, and $-0.38$. The numbers were converging,
but we stopped short of asking where they converge to. The difference quotient
measures average steepness over a finite interval. What we really want is the
steepness at a single point, the instantaneous slope of the rail precisely at
$x_0 = 5~\text{cm}$. To find it, we must let the step size shrink all the way
to zero and examine what the difference quotient approaches in that process.

```{admonition} Learning goals
:class: attention
* [ ] You understand the concept of the **limit** of the difference quotient
  as $h \to 0$.
* [ ] You know the **differential quotient**
  $f'(x_0) = \lim_{h \to 0} \dfrac{f(x_0 + h) - f(x_0)}{h}$
  as the instantaneous rate of change of $f$ at the point $x_0$.
* [ ] You can interpret the differential quotient geometrically as the slope
  of the **tangent line** to the graph of $f$ at the point $(x_0, f(x_0))$.
```

## What happens as the step size approaches zero?

At the end of section 5.1 we observed that the secant line through
$P_1 = (5,\, f(5))$ and $P_2 = (5 + \Delta x,\, f(5 + \Delta x))$ rotates as
$\Delta x$ decreases. The table below continues that observation with even
smaller step sizes.

| Step size $\Delta x$ [cm] | Difference quotient |
| ------------------------- | ------------------- |
| 2.0 | $-0.36$ |
| 1.0 | $-0.38$ |
| 0.5 | $-0.39$ |
| 0.1 | $-0.398$ |
| 0.01 | $-0.3998$ |
| 0.001 | $-0.39998$ |

The values are clearly settling toward $-0.4$. They never reach it for any
finite $\Delta x$, but they get arbitrarily close. In mathematics we express
this by saying that the difference quotient has a **limit** of $-0.4$ as
$\Delta x$ approaches zero, and we write

\begin{equation*}
\lim_{\Delta x \to 0} \frac{f(5 + \Delta x) - f(5)}{\Delta x} = -0.4.
\end{equation*}

This limiting value is the instantaneous steepness of the rail at
$x_0 = 5~\text{cm}$. It is not an average over any interval, no matter how
short. It is the slope at a single point.

## What is the differential quotient?

The limiting process above can be applied at any point $x_0$ in the domain,
not only at $x_0 = 5$. For a general function $f$ and a general point $x_0$,
we define the limit of the difference quotient as the **differential
quotient** of $f$ at $x_0$.

```{admonition} What is ... the differential quotient?
:class: note
Let $f$ be a function defined on an open interval containing $x_0$. The
**differential quotient** of $f$ at $x_0$ is

\begin{equation*}
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h},
\end{equation*}

provided this limit exists. It is also called the **derivative** of $f$ at
$x_0$, and we read $f'(x_0)$ as "$f$ prime at $x_0$".
```

The differential quotient and the derivative at a point are two names for
the same object. The notation $f'(x_0)$ was introduced by Lagrange and is
the most common in engineering mathematics. An alternative notation due to
Leibniz writes the same quantity as $\dfrac{df}{dx}\big|_{x_0}$, which makes
the limit of the ratio $\Delta f / \Delta x$ visible in the symbol itself.
Both notations appear in engineering literature, and we will use them
interchangeably.

## How do we compute the differential quotient for the marble track?

We now verify the limiting value $-0.4$ algebraically, using the same
technique that the German algebraist Carl Friedrich Gauss might have called
"expanding and cancelling." This method works for any polynomial and
produces the exact limit without any guesswork.

Our height function is $f(x) = 0.02\,x^2 - 0.6\,x + 6$. We want to compute
$f'(5)$. We start from the difference quotient and expand the numerator by
substituting $x_0 + \Delta x = 5 + \Delta x$ into the function:

\begin{align*}
f(5 + \Delta x)
&= 0.02\,(5 + \Delta x)^2 - 0.6\,(5 + \Delta x) + 6 \\
&= 0.02\,(25 + 10\,\Delta x + (\Delta x)^2) - 3 - 0.6\,\Delta x + 6 \\
&= 0.5 + 0.2\,\Delta x + 0.02\,(\Delta x)^2 - 3 - 0.6\,\Delta x + 6 \\
&= 3.5 - 0.4\,\Delta x + 0.02\,(\Delta x)^2.
\end{align*}

Subtracting $f(5) = 3.5$ and dividing by $\Delta x$:

\begin{align*}
\frac{f(5 + \Delta x) - f(5)}{\Delta x}
&= \frac{3.5 - 0.4\,\Delta x + 0.02\,(\Delta x)^2 - 3.5}{\Delta x} \\
&= \frac{-0.4\,\Delta x + 0.02\,(\Delta x)^2}{\Delta x} \\
&= \frac{\Delta x\,(-0.4 + 0.02\,\Delta x)}{\Delta x} \\
&= -0.4 + 0.02\,\Delta x.
\end{align*}

We factored $\Delta x$ out of the numerator and cancelled it with the
$\Delta x$ in the denominator. The result is a simple linear expression with
no division by zero. Letting $\Delta x \to 0$ gives

\begin{equation*}
f'(5) = \lim_{\Delta x \to 0} (-0.4 + 0.02\,\Delta x) = -0.4.
\end{equation*}

This confirms the numerical observation from the table. At $x_0 = 5~\text{cm}$
the rail is descending at an instantaneous rate of $0.4~\text{cm}$ of height
per centimetre of horizontal travel, and the negative sign tells us it is
indeed descending rather than rising.

As a consistency check we can anticipate what the same calculation would give
at the vertex $x_0 = 15~\text{cm}$. The rail is neither rising nor falling at
its lowest point, so we expect the instantaneous slope to be zero there. The
next section derives the general formula $f'(x) = 0.04\,x - 0.6$ for all $x$,
from which $f'(15) = 0.04 \cdot 15 - 0.6 = 0$ follows immediately, confirming
this expectation.

## What does the differential quotient look like on the graph?

In section 5.1 we saw the secant line rotating as $\Delta x$ decreased.
The differential quotient is the slope that the secant approaches in the
limit. The line with exactly that slope, passing through the point
$P_1 = (5,\, f(5)) = (5,\, 3.5)$, is called the **tangent line** to the
curve at $x_0 = 5$.

The tangent line touches the parabola at $P_1$ and nowhere else in its
immediate vicinity. Its slope, $-0.4$, is the best possible linear
description of how the rail behaves right at that point. If we zoomed in
on the graph around $P_1$, magnifying more and more, the parabola would
look increasingly straight, and that straight line would be the tangent.
This is why the derivative is sometimes described as the slope of the curve
at a point: the curve and its tangent are indistinguishable under sufficient
magnification.

The full equation of the tangent line, and its role as a linear approximation
of the function, will be developed in section 5.5. For now it is enough to
know that the differential quotient $f'(x_0)$ is its slope.

```{raw} html
<!--
  SVELTE APP: "Convergence to the differential quotient"

  Two panels side by side (or stacked on narrow screens).

  LEFT PANEL: convergence table
    A live table with six rows, one for each of:
      Δx = 2, 1, 0.5, 0.1, 0.01, 0.001
    Columns: Δx | f(x0 + Δx) | Δf | difference quotient Δf/Δx
    All values computed from f(x) = 0.02x² - 0.6x + 6.
    A slider lets the student choose x0 in [0, 28], default 5.
    The bottom row of the table is highlighted and labelled
    "approaches f'(x0) = ..." with the analytical value 0.04·x0 - 0.6.

  RIGHT PANEL: graph
    The parabola f(x) = 0.02x² - 0.6x + 6 on [0, 30] in dark blue.
    The point P1 = (x0, f(x0)) as a filled dot (orange).
    A second point P2 = (x0 + Δx, f(x0 + Δx)) as a filled dot (red),
    connected to P1 by the secant line (red).
    The tangent line at x0 (green dashed), always visible.
    A small dropdown or button row lets the student pick which Δx row
    in the table is currently highlighted, so P2 jumps to the
    corresponding position and the secant updates.

  Info tile below both panels:
    "Tangent slope f'(x0)" showing 0.04·x0 - 0.6 to 3 decimal places.

  Purpose: students see the algebraic convergence in the table and the
  geometric rotation of the secant in the graph simultaneously. Moving
  x0 to 15 shows the slope approaching 0, confirming that the tangent is
  horizontal at the vertex.
-->
```

## Summary and outlook

We have defined the differential quotient as the limit of the difference
quotient as the step size approaches zero. For the parabolic marble track at
$x_0 = 5~\text{cm}$, this limit is $-0.4$, a result we confirmed both
numerically from a convergence table and algebraically by expanding and
cancelling. Geometrically, the differential quotient is the slope of the
tangent line to the curve at the chosen point. In the computation above we
fixed $x_0 = 5$ and obtained a single number. But the same algebraic steps
work for any $x_0$, and the result would be a formula in $x_0$ rather than
a single value. That formula is called the derivative function, and
constructing it is the subject of the next section.
