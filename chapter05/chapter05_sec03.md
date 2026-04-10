---
authors:
  - name: Simone Gramsch
---

# 5.3 The Derivative Function

In section 5.2 we computed the differential quotient of the parabolic marble
track at the single point $x_0 = 5~\text{cm}$ and found $f'(5) = -0.4$. The
closing observation was that the same algebraic steps would work for any choice
of $x_0$, and the result would be a formula rather than a single number. We now
carry out that calculation. The outcome is a new function that assigns to every
position on the track the instantaneous slope at that position, a complete map
of the track's steepness.

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **derivative function**
  \begin{equation*}
  f'(x) = \lim_{h \to 0} \dfrac{f(x + h) - f(x)}{h}.
  \end{equation*}
* [ ] You are familiar with the standard notations for the derivative:
  $f'(x)$, $\dfrac{df}{dx}$, and $\dot{f}(t)$.
* [ ] You can compute the derivative function of a polynomial directly from
  the limit definition.
```

## From one point to the whole domain

In section 5.2 we fixed $x_0 = 5$ before expanding $f(x_0 + h)$. The number
$5$ appeared repeatedly in the algebra, but it played no special role: every
step would have worked identically with any other value. The only thing that
changes when we replace $5$ by a general variable $x$ is that the final answer
is no longer a number but an expression in $x$.

We set up the difference quotient for our height function
$f(x) = 0.02\,x^2 - 0.6\,x + 6$ at a general point $x$:

\begin{align*}
f(x + h)
&= 0.02\,(x + h)^2 - 0.6\,(x + h) + 6 \\
&= 0.02\,(x^2 + 2xh + h^2) - 0.6\,x - 0.6\,h + 6 \\
&= 0.02\,x^2 + 0.04\,x h + 0.02\,h^2 - 0.6\,x - 0.6\,h + 6.
\end{align*}

Subtracting $f(x) = 0.02\,x^2 - 0.6\,x + 6$, the terms that do not involve
$h$ cancel completely:

\begin{align*}
f(x + h) - f(x)
&= 0.04\,xh + 0.02\,h^2 - 0.6\,h \\
&= h\,(0.04\,x - 0.6 + 0.02\,h).
\end{align*}

Dividing by $h$ and taking the limit:

\begin{align*}
f'(x)
&= \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
= \lim_{h \to 0} \frac{h\,(0.04\,x - 0.6 + 0.02\,h)}{h} \\
&= \lim_{h \to 0} (0.04\,x - 0.6 + 0.02\,h)
= 0.04\,x - 0.6.
\end{align*}

The derivative function of our parabolic track is

\begin{equation*}
f'(x) = 0.04\,x - 0.6, \quad x \in [0, 30].
\end{equation*}

This is a linear function. The derivative of a polynomial of degree 2 is a
polynomial of degree 1 — one degree lower. We will see in the next chapter
that this pattern holds for every power function.

We can immediately verify the earlier result: substituting $x = 5$ gives
$f'(5) = 0.04 \cdot 5 - 0.6 = 0.2 - 0.6 = -0.4$, which agrees exactly with
the value computed by the longer route in section 5.2.

## What is the derivative function?

The procedure above can be applied to any function $f$, not only to our
specific parabola. If the limit of the difference quotient exists at every
point of the domain, the assignment $x \mapsto f'(x)$ defines a new function.

```{admonition} What is ... the derivative function?
:class: note
Let $f$ be defined on an open interval $I$. If the limit

\begin{equation*}
f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
\end{equation*}

exists for every $x \in I$, then the function $f': I \to \mathbb{R}$,
$x \mapsto f'(x)$, is called the **derivative function** of $f$. The process
of computing $f'$ from $f$ is called **differentiation**.
```

A few points are worth noting. First, $f'$ is a genuine function in its own
right, with its own domain, range, zeros, and graph. Second, the domain of
$f'$ can be smaller than the domain of $f$: if the limit fails to exist at
some point, that point is excluded from the domain of $f'$. We examine exactly
this possibility in section 5.4. Third, differentiating $f'$ a second time
produces the **second derivative** $f''$, which measures how rapidly the slope
itself is changing. These higher derivatives will appear naturally in later
chapters when we study approximation and optimization.

## What does the derivative function reveal about the track?

We now have a formula $f'(x) = 0.04\,x - 0.6$ that we can evaluate at every
position along the track. The following table records the slope at several
points of interest.

| Position $x$ [cm] | $f'(x)$ | Interpretation |
| --- | --- | --- |
| $0$ | $-0.6$ | steepest descent, at the starting block |
| $5$ | $-0.4$ | falling, confirms section 5.2 |
| $15$ | $0$ | horizontal, at the lowest point |
| $25$ | $+0.4$ | rising, symmetric counterpart of $x = 5$ |
| $30$ | $+0.6$ | steepest ascent, at the finishing block |

Three observations stand out. The derivative is zero at $x = 15$, the vertex
of the parabola. This is not a coincidence: the vertex is the point where the
track transitions from descending to ascending, so its instantaneous slope must
be zero there. We will make this observation the foundation of optimization in
a later chapter, where finding zeros of the derivative is the key technique for
locating minima and maxima of any differentiable function.

The derivative is negative for $x < 15$ and positive for $x > 15$. Comparing
this with the definition of monotonicity from section 3.2, we see that the
derivative gives us a precise algebraic criterion for what we described there
geometrically: a function is increasing on an interval where $f'(x) > 0$ and
decreasing where $f'(x) < 0$.

The values at $x = 5$ and $x = 25$ are equal in magnitude and opposite in
sign: $f'(5) = -0.4$ and $f'(25) = +0.4$. The same holds for $x = 0$ and
$x = 30$. This reflects the symmetry of the parabola about its axis at
$x = 15$: the track rises on the right at the same rate at which it falls on
the left.

<!--
  SVELTE APP: "Function and its derivative side by side"

  Two coordinate systems stacked vertically, sharing the same x-axis range
  [0, 30] and linked by a vertical movable cursor at x = x0.

  TOP PANEL: graph of f(x) = 0.02x² - 0.6x + 6
    - The parabola in dark blue.
    - The tangent line at x0 (green dashed), updating live as x0 moves.
    - A filled dot at (x0, f(x0)) in orange.
    - The slope value f'(x0) = 0.04·x0 - 0.6 shown as a label next to
      the tangent line.

  BOTTOM PANEL: graph of f'(x) = 0.04x - 0.6
    - The straight line in red.
    - A filled dot at (x0, f'(x0)) in orange, directly below the dot in
      the top panel.
    - A horizontal dashed reference line at y = 0, labelled "f'(x) = 0".

  A single slider controls x0 across [0, 30], default 5.

  When the student drags x0:
    - The tangent on the top panel rotates.
    - The dot on the bottom panel slides along the red line.
    - Both dots stay vertically aligned, making the correspondence
      between "tangent slope at x0" and "value of f'(x0)" concrete.

  Preset buttons at x0 = 0, 5, 15, 25, 30 highlight the five entries
  in the table above.

  Purpose: the most important conceptual leap in this section is that
  f'(x) is itself a function with a graph. This app makes that leap
  visual: the height of the red dot equals the slope of the green line,
  at every x simultaneously.
-->

## How is the derivative written?

The derivative function $f'$ can be written in several equivalent notations.
All three appear in engineering literature and textbooks, and it is important
to recognise each of them.

The **Lagrange notation** $f'(x)$ is read as "$f$ prime of $x$". It is concise
and is the standard choice in this course. The derivative at a specific point
$x_0$ is written $f'(x_0)$.

The **Leibniz notation** $\dfrac{df}{dx}$ is read as "$df$ by $dx$" or "the
derivative of $f$ with respect to $x$". It makes the limit of the ratio
$\Delta f / \Delta x$ visible in the symbol itself and is particularly
expressive when we want to name the variable of differentiation explicitly.
The evaluated form $\dfrac{df}{dx}\big|_{x_0}$ gives the derivative at the
specific point $x_0$. Leibniz notation is especially common in physics and
in the formulation of differential equations.

The **Newton notation** $\dot{f}(t)$ is read as "$f$ dot". It is used
exclusively when the independent variable is time $t$. In mechanical
engineering, if $s(t)$ is the position of a component as a function of time,
then $\dot{s}(t)$ is its velocity and $\ddot{s}(t)$ is its acceleration. The
dot notation is compact and is standard in dynamics, control engineering, and
any field where time derivatives appear frequently.

All three notations refer to the same mathematical object. For our marble
track, where the independent variable is position $x$, we use Lagrange or
Leibniz notation:

\begin{equation*}
f'(x) = \frac{df}{dx} = 0.04\,x - 0.6.
\end{equation*}

If instead we imagined the marble moving along the track and described its
height as a function of time $t$, we would write $\dot{f}(t)$ for the rate
of change of height with respect to time.

## Summary and outlook

We have extended the differential quotient from a number at one point to a
function defined across the entire domain. For the parabolic marble track,
the limit calculation at a general point $x$ produces the derivative function
$f'(x) = 0.04\,x - 0.6$, a linear function that encodes the instantaneous
slope of the track at every position. The zero of $f'$ at $x = 15$ marks the
vertex, the negative values for $x < 15$ confirm the descending left half, and
the positive values for $x > 15$ confirm the ascending right half. The
calculation we performed assumed without question that the limit exists at every
point of the domain. For our smooth parabola this is true, but it need not be
true in general. A track with a sharp kink, for instance, has no well-defined
tangent direction at the kink, and therefore no derivative there. Understanding
exactly when a function is differentiable, and what goes wrong when it is not,
is the subject of the next section.
