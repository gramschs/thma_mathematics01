---
authors:
  - name: Simone Gramsch
---

# 5.4 Differentiability and Continuity

At the end of section 5.3 we noted that the limit defining the derivative does
not always exist. Our parabolic track is smooth everywhere, so the derivative
function $f'(x) = 0.04\,x - 0.6$ was well defined across the entire domain
without difficulty. But in section 3.3 we built a marble track with a plateau,
where a descending rail meets a flat section and the flat section meets a second
descending rail. At each junction the track has a sharp kink. A ball rolling
over such a kink has a well-defined height on either side, but there is no
single tangent direction at the kink itself. Understanding precisely when a
derivative exists, and why it sometimes does not, is the goal of this section.

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of **differentiability** at a point and on an
  open interval.
* [ ] You know that every differentiable function is also **continuous**, and
  you understand why the converse is not true in general.
* [ ] You can identify points where a function is continuous but not
  differentiable, such as **corners**, **cusps**, and points with a
  **vertical tangent**.
```

## What happens at the junction between two track segments?

We return to the piecewise marble track from section 3.3. Writing the height
function as $f$ for consistency with this chapter, the track has three
segments:

\begin{equation*}
f(x) = \begin{cases}
-0.25\,x + 6, & x \in [0, 8], \\
4,             & x \in (8, 12], \\
-\dfrac{1}{3}\,x + 8, & x \in (12, 24].
\end{cases}
\end{equation*}

At $x = 8$ the first segment meets the plateau. From the left, the rail is
descending with slope $-0.25$. From the right, the plateau is flat with
slope $0$. The function value at the junction is $f(8) = 4$ from both
sides, so the track is continuous there. But the slopes disagree.

We can see this disagreement precisely by computing the difference quotient
at $x_0 = 8$ from each side separately. For a small step $h < 0$ (approaching
from the left) we use the first segment:

\begin{equation*}
\frac{f(8 + h) - f(8)}{h}
= \frac{(-0.25(8 + h) + 6) - 4}{h}
= \frac{-0.25\,h}{h} = -0.25.
\end{equation*}

This value is the same for every $h < 0$, no matter how small. The
difference quotient from the left approaches $-0.25$ as $h \to 0^-$.

For a small step $h > 0$ (approaching from the right) we use the plateau:

\begin{equation*}
\frac{f(8 + h) - f(8)}{h} = \frac{4 - 4}{h} = 0.
\end{equation*}

The difference quotient from the right is identically $0$ for every $h > 0$,
so it approaches $0$ as $h \to 0^+$.

The two one-sided limits of the difference quotient, $-0.25$ from the left and
$0$ from the right, are different. For the overall limit to exist, the
difference quotient would need to approach the same value regardless of the
direction from which $h$ approaches zero. Since it does not, the limit does
not exist, and $f$ has no derivative at $x = 8$.

The same calculation at $x = 12$, where the plateau meets the second descending
segment, gives a left-hand limit of $0$ and a right-hand limit of
$-\tfrac{1}{3} \approx -0.333$. Again the two sides disagree, and again the
derivative does not exist.

## What is differentiability?

The example above shows what it means for the limit to fail: the difference
quotient approaches different values depending on the direction of approach.
We now state the condition for success as a formal definition.

```{admonition} What is ... differentiability?
:class: note
A function $f$ is called **differentiable at a point $x_0$** if the limit

\begin{equation*}
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
\end{equation*}

exists as a finite real number. This means the difference quotient must
approach the same finite value whether $h$ approaches zero from above or
from below.

A function is called **differentiable on an open interval $I$** if it is
differentiable at every point of $I$.
```

The phrase "finite real number" in the definition is important. Even if the
difference quotient grows without bound as $h \to 0$, the limit is not finite
and the function is not considered differentiable at that point. We will
encounter this case when we discuss vertical tangents below.

Our parabolic track $f(x) = 0.02\,x^2 - 0.6\,x + 6$ is differentiable on
the open interval $(0, 30)$: the limit calculation in section 5.3 produced
the finite value $f'(x) = 0.04\,x - 0.6$ at every point. The piecewise track
is differentiable on each of the three open segments but not at $x = 8$ or
$x = 12$.

## Does continuity guarantee differentiability?

The piecewise track is continuous at $x = 8$: the height approaches $4$ from
both sides and equals $4$ at the point. Yet the function is not differentiable
there. Continuity is therefore not sufficient for differentiability. The converse
question is more rewarding: does differentiability guarantee continuity?

The answer is yes. If $f$ is differentiable at $x_0$, it is automatically
continuous there. To see why, we write the change in function value as a
product:

\begin{equation*}
f(x_0 + h) - f(x_0)
= \frac{f(x_0 + h) - f(x_0)}{h} \cdot h.
\end{equation*}

As $h \to 0$, the first factor approaches $f'(x_0)$, a finite number, and
the second factor approaches $0$. The product therefore approaches $0$,
which means $f(x_0 + h) \to f(x_0)$. That is exactly the definition of
continuity at $x_0$.

```{admonition} What is ... the relationship between differentiability and continuity?
:class: note
If $f$ is differentiable at $x_0$, then $f$ is also continuous at $x_0$.

The converse is false: a function can be continuous at a point without being
differentiable there. Continuity prevents jumps; differentiability additionally
requires a unique, finite tangent slope.
```

In practical terms: a jump discontinuity (a sudden step in the function value)
makes differentiability impossible, since the difference quotient would grow
without bound as $h \to 0$ from one side. But removing the jump, that is,
making the function continuous, is only the first requirement. The slopes must
also agree from both sides.

## What other shapes can prevent differentiability?

The corner at a track junction is the most common failure of differentiability
in engineering models, but it is not the only one. Two further cases are worth
knowing.

**Corner.** This is the case we have already analysed in detail. The
function is continuous at $x_0$, but the difference quotient approaches
different finite values from the left and from the right. The function
$f(x) = |x|$ at $x_0 = 0$ is the simplest example: the left-hand limit of
the difference quotient is $-1$ and the right-hand limit is $+1$. The graph
has a sharp V-shape with no unique tangent direction at the tip.

**Cusp.** A cusp is a sharper version of a corner. The function is
continuous at $x_0$, but the difference quotient grows without bound in
magnitude from both sides, with opposite signs. The function
$f(x) = x^{2/3}$ at $x_0 = 0$ is a standard example: as $h \to 0^-$ the
difference quotient tends to $-\infty$, and as $h \to 0^+$ it tends to
$+\infty$. The graph comes to a pointed tip that is steeper than any finite
slope.

**Vertical tangent.** Here the difference quotient grows without bound
from both sides in the same direction. The function $f(x) = x^{1/3}$ at
$x_0 = 0$ behaves this way: as $h \to 0$ the difference quotient grows like
$h^{-2/3} \to +\infty$ regardless of the sign of $h$. Geometrically the
tangent line would be vertical, which is excluded by the requirement that
the limit be a finite real number. On a marble track this would correspond
to a section of rail that drops straight down, a physical impossibility and
a mathematical signal that the function model is being pushed beyond its
valid domain.

<!--
  SVELTE APP: "One-sided difference quotients at a corner"

  The piecewise track f(x) from this section, plotted on [0, 24].

  A slider selects x0 across [0.5, 23.5], default 8.

  For each x0 the app computes two difference quotients simultaneously,
  one with h = +0.5 (right side, shown in red) and one with h = -0.5
  (left side, shown in blue), and draws both secant lines on the graph.
  As the student drags x0 toward 8 or 12, the two secant lines are visibly
  different slopes that do not converge to a common line.

  A second slider controls the magnitude of h across [0.01, 3], default 0.5.
  Reducing h shows the one-sided quotients stabilising at different values
  at the corners, and at the same value on the smooth segments.

  Info tiles:
    - "Left quotient" (h < 0), rounded to 3 decimal places.
    - "Right quotient" (h > 0), rounded to 3 decimal places.
    - "Differentiable?" shown as YES (green) when the two quotients agree to
      within 0.01, and NO (red) when they differ by more.

  Preset buttons at x0 = 4, 8, 10, 12, 18 let the student jump to
  representative positions: a smooth interior point on each of the three
  segments and the two corners.

  Purpose: students see directly that differentiability is a two-sided
  condition. At a smooth point the two secant lines converge to the same
  tangent; at a corner they lock onto different slopes no matter how small
  h becomes.
-->

## Additional Material

```{dropdown} Video "Differentiability and continuity" by Khan Acdemy
<iframe width="887" height="499" src="https://www.youtube.com/embed/xuAiQOzIkWY"
title="Differentiability and continuity | Derivatives introduction | AP Calculus AB |
Khan Academy" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Continuity and Differentiability" by The Organic Chemistry Tutor
<iframe width="887" height="499" src="https://www.youtube.com/embed/fml0-ELYLaE"
title="Continuity and Differentiability" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Summary and outlook

We have seen that differentiability is a stronger condition than continuity.
Every differentiable function is continuous, but the piecewise marble track
shows that continuity does not guarantee differentiability: the function is
continuous at $x = 8$ and $x = 12$, yet the two-sided limit of the difference
quotient fails at both points because the one-sided limits are unequal.
Beyond corners, cusps and vertical tangents produce the same failure by
different geometries. With the concept of differentiability in place, we can
now return to the smooth parabolic track with confidence: at every interior
point the limit exists, is finite, and equals the value given by the derivative
function derived in section 5.3. The next section uses this fact to construct
the tangent line at any chosen point, the straight line that best approximates
the curve locally and that will become our first practical tool of differential
calculus.
