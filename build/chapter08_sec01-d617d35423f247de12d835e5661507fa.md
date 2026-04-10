---
authors:
  - name: Simone Gramsch
---

# 8.1 Local and Global Extrema

The tools assembled in chapter 7 allow us to analyze the slope and curvature
of a function at every point of its domain. We now put them to work on the
problem that motivates much of engineering design: finding the value of a
variable that makes some quantity as large or as small as possible. Where the
first derivative identifies intervals of increase and decrease, it also singles
out the special interior points where the slope vanishes. The second derivative,
whose sign we used in chapter 7 to classify intervals as convex or concave,
now tells us whether each of those special points is a peak or a trough.

```{admonition} Learning goals
:class: attention
* [ ] You know the definitions of **local maximum**, **local minimum**, and **global extremum** of a function.
* [ ] You know the **necessary condition** for a local extremum: $f'(x_0) = 0$ at a **critical point** $x_0$.
* [ ] You know the **sufficient conditions** using the second derivative: $f''(x_0) > 0$ implies a local minimum and $f''(x_0) < 0$ implies a local maximum at a critical point.
* [ ] You can find and classify the local extrema of a given differentiable function and determine which of them is the global extremum on a closed interval.
```

## How does the power delivered to a load depend on resistance?

A battery with electromotive force $E = 12~\text{V}$ and internal resistance
$r = 3~\Omega$ is connected to a variable load resistor of resistance $R$.
The current through the circuit is $I = E / (R + r)$, and the power delivered
to the load is

\begin{equation*}
P(R) = I^2 R = \frac{E^2 R}{(R + r)^2} = \frac{144\,R}{(R + 3)^2},
\quad R \in [0, 10]~\Omega.
\end{equation*}

The interval $[0, 10]~\Omega$ represents the practical range of available
load resistors. At $R = 0$ (short circuit) all power is dissipated inside
the battery and none reaches the load: $P(0) = 0$. As $R$ increases, the
power rises. But the current simultaneously decreases, and eventually the
power must begin to fall. *There must be an optimal load resistance that
maximises the power delivered.*

We locate this optimum by differentiating, using the quotient rule from
chapter 6:

\begin{equation*}
P'(R)
= 144 \cdot \frac{(R + 3)^2 - R \cdot 2(R + 3)}{(R + 3)^4}
= 144 \cdot \frac{(R + 3) - 2R}{(R + 3)^3}
= \frac{144(3 - R)}{(R + 3)^3}.
\end{equation*}

Setting $P'(R) = 0$ gives $3 - R = 0$, so $R = 3~\Omega$. For $R < 3$ the
numerator $3 - R$ is positive and $P' > 0$: the power is still rising.
For $R > 3$ the numerator is negative and $P' < 0$: the power is falling.
The function climbs to a peak at $R = 3$ and then descends, which is exactly
what the sign of $P'$ confirms.

## What is a local extremum?

The point $R = 3$ is special: the power neither rises nor falls there, but
transitions from rising to falling. A function that changes from increasing
to decreasing at an interior point has a **local maximum** there. Conversely,
a function that changes from decreasing to increasing has a **local minimum**
there. Together these are called the **local extrema** of the function.

If $f$ is differentiable at an interior point $x_0$ and has a local extremum
there, the tangent line must be horizontal: the slope is neither positive
(which would mean $f$ is still rising) nor negative (which would mean $f$ is
still falling). The condition $f'(x_0) = 0$ is therefore necessary for a local
extremum. A point where this condition holds is called a **critical point** of $f$.

```{admonition} What is ... a local extremum?
:class: note
Let $f$ be defined on an interval $I$ and differentiable at an interior
point $x_0$.

$f$ has a **local maximum** at $x_0$ if $f(x_0) \geq f(x)$ for all $x$ in
some open interval around $x_0$.

$f$ has a **local minimum** at $x_0$ if $f(x_0) \leq f(x)$ for all $x$ in
some open interval around $x_0$.

A necessary condition for either is that $x_0$ is a **critical point**:
$f'(x_0) = 0$.
```

The condition $f'(x_0) = 0$ is necessary but not sufficient. A critical point
need not be a local extremum at all: it could be an inflection point of the kind
studied in section 7.4, where the slope vanishes momentarily but does not change
sign. We therefore need a second condition to classify a critical point once we
have found it.

## How does the second derivative classify a critical point?

At a critical point $x_0$, the value $f'(x_0) = 0$ tells us the slope is
zero but nothing about what the slope does next. The second derivative
$f''(x_0)$ fills exactly this gap. If $f''(x_0) > 0$, the slope is
increasing through zero: the function descended into $x_0$ from the left and
rises away to the right, which is the signature of a local minimum. If
$f''(x_0) < 0$, the slope is decreasing through zero: the function rose into
$x_0$ and then descends, which is the signature of a local maximum.

```{admonition} What is ... the second derivative test?
:class: note
Let $f$ be twice differentiable at a critical point $x_0$ where $f'(x_0) = 0$.

If $f''(x_0) > 0$, then $f$ has a **local minimum** at $x_0$.

If $f''(x_0) < 0$, then $f$ has a **local maximum** at $x_0$.

If $f''(x_0) = 0$, the test is inconclusive and the sign of $f'$ on either
side of $x_0$ must be checked directly.
```

We apply the test to $R = 3$ on the power function. Differentiating
$P'(R) = 144(3 - R)/(R + 3)^3$ once more with the quotient rule:

\begin{equation*}
P''(R)
= 144 \cdot \frac{-(R + 3)^3 - (3 - R) \cdot 3(R + 3)^2}{(R + 3)^6}
= 144 \cdot \frac{-(R + 3) - 3(3 - R)}{(R + 3)^4}
= \frac{144(2R - 12)}{(R + 3)^4}.
\end{equation*}

At $R = 3$:

\begin{equation*}
P''(3) = \frac{144(6 - 12)}{6^4} = \frac{144 \cdot (-6)}{1296} = -\frac{2}{3} < 0.
\end{equation*}

The second derivative is negative, confirming that $R = 3~\Omega$ is a local
maximum. The maximum power delivered to the load is

\begin{equation*}
P(3) = \frac{144 \cdot 3}{(3 + 3)^2} = \frac{432}{36} = 12~\text{W}.
\end{equation*}

This result carries a name in electrical engineering: the **maximum power
transfer theorem**, which states that maximum power is delivered to the load
when the load resistance equals the internal resistance, $R = r$. The theorem
is a direct consequence of setting the first derivative to zero and verifying
the sign of the second.

To complete the picture with a local minimum, we recall the parabolic marble
track from chapter 5: $f(x) = 0.02x^2 - 0.6x + 6$ with $f'(x) = 0.04x - 0.6$.
The critical point is at $x = 15$, where $f''(15) = 0.04 > 0$: positive second
derivative, so a local minimum. The track reaches its lowest point at
$x = 15~\text{cm}$, the vertex of the parabola.

## What is the global extremum on a closed interval?

A local extremum is the best value in a neighbourhood of $x_0$. The engineer
usually needs the best value on the entire domain of interest: the **global
maximum** or **global minimum**. On a closed interval $[a, b]$ the global
extremum is found by comparing three types of candidate: the critical points
inside the interval and the two endpoints, since the function may be largest
or smallest at a boundary.

For the power function on $[0, 10]$, there is one interior critical point
at $R = 3$ with $P(3) = 12~\text{W}$. The endpoint values are $P(0) = 0$ and

\begin{equation*}
P(10) = \frac{144 \cdot 10}{13^2} = \frac{1440}{169} \approx 8.5~\text{W}.
\end{equation*}

| Candidate | $R$ [$\Omega$] | $P(R)$ [W] |
| --- | --- | --- |
| Left endpoint | $0$ | $0$ |
| Critical point | $3$ | $12$ |
| Right endpoint | $10$ | $\approx 8.5$ |

The largest value in the table is $12~\text{W}$ at $R = 3~\Omega$: the
global maximum. The smallest is $0~\text{W}$ at $R = 0$: the global minimum.
No other candidates exist inside the interval, so the comparison is complete.

```{admonition} What is ... the global extremum on a closed interval?
:class: note
Let $f$ be continuous on a closed interval $[a, b]$ and differentiable on its
interior. The **global maximum** (or **global minimum**) of $f$ on $[a, b]$
is the largest (or smallest) value in the set consisting of $f(a)$, $f(b)$,
and $f(x_0)$ for every critical point $x_0 \in (a, b)$.
```

<!--
  SVELTE APP: "Power and load resistance"

  Main panel: the graph of P(R) = 144R/(R+3)² on [0, 10].
  A movable vertical cursor at R = R0 (slider, default R0 = 3).
  The tangent line to P at R0, shown as a dashed green line.
  A filled dot at (R0, P(R0)) in orange.

  Marker at R = 3: a vertical dashed line labelled "R = r = 3 Ω"
  with the annotation "Maximum power transfer".

  Three info tiles below the graph:
    - "P(R₀)" showing the power in watts to 2 decimal places.
    - "P'(R₀)" showing the derivative value, coloured blue when positive,
      red when negative, and green when near zero.
    - "P''(R₀)" showing the second derivative, labelled "local max" when
      negative (near the peak).

  A second mini-panel shows the three candidate values in a small table:
  P(0), P(R0) (updating with the slider), and P(10), with the global max
  highlighted in green.

  Purpose: students can drag R0 and see P', P'' update simultaneously.
  The sign flip of P' at R = 3 and the negative P'' confirm the local max
  interactively. The table reinforces the global-extremum procedure.
-->

## Where do extrema appear in engineering?

The maximum power transfer theorem is one instance of a universal pattern:
a performance quantity that benefits from increasing one parameter in one way
but is hurt by it in another, producing a peak at an intermediate value.

In aerodynamics, the lift-to-drag ratio of a wing depends on the angle of
attack. At low angles there is little lift; at high angles the drag grows
faster than the lift. The maximum lift-to-drag ratio, the most efficient
cruising condition, is found by differentiating the ratio and setting the
derivative to zero. In chemical engineering, the net yield of a reactor often
depends on temperature: higher temperature speeds the desired reaction but also
the competing side reactions, producing a yield maximum at an optimal operating
temperature. In each case the mathematical procedure is identical to the one
we performed for the power function.

## Summary and outlook

We have defined local extrema as the points where a function transitions from
increasing to decreasing or vice versa, identified critical points as their
necessary condition, and established the second derivative test as the
classification tool. For the maximum power transfer problem, the critical
point at $R = 3~\Omega$ is a local and global maximum with $P(3) = 12~\text{W}$.
The marble track contributes the contrasting case: a local minimum at the
vertex, confirmed by a positive second derivative.

With extrema fully characterised, we now have all the ingredients for a
complete portrait of any differentiable function. The next section assembles
them into a systematic procedure, called curve sketching, that produces a
qualitatively accurate graph from the derivatives alone.
