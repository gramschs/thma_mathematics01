---
authors:
  - name: Simone Gramsch
---

# Properties of Functions

In the previous section we described the height of a ball on a straight
inclined rail as a function. Now we extend the marble track system by building
different track configurations. Each new track will reveal a property that
helps us understand and classify the behaviour of mathematical functions.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You can determine the **zeros** of a function.
* [ ] You can check whether a function is **monotonically increasing** or
  **monotonically decreasing** (strictly or non-strictly) on a given interval.
* [ ] You can check whether a function is **bounded** above and/or below.
* [ ] You can check whether a function is **even** (symmetric about the y-axis)
  or **odd** (point-symmetric about the origin).
* [ ] You know what **periodicity** means and can identify the period of a given
  function.
```

## Zeros — where does the ball reach the ground?

Our straight inclined rail starts at a height of $6~\text{cm}$ and descends
steadily. At some point the ball reaches the table surface, that is, the height
becomes zero. For our height function $h(x) = -\frac{1}{4}x + 6$ we can
calculate this position by setting $h(x) = 0$ and solving for $x$:

\begin{equation*}
-\frac{1}{4}x + 6 = 0 \quad \Rightarrow \quad x = 24~\text{cm.}
\end{equation*}

The ball reaches the table surface exactly at the finishing block. The position
$x = 24~\text{cm}$ is called a **zero** of the height function.

```{admonition} What is ... a zero?
:class: note
A **zero** of a function $f$ is a value $x_0$ in the domain for which

\begin{equation*}
f(x_0) = 0.
\end{equation*}

Geometrically, a zero is a point where the graph of the function crosses or
touches the horizontal axis.
```

A function can have no zeros, exactly one zero, or several zeros, depending on
its shape. Whether zeros exist, and how many, is one of the first questions we
ask when analysing a function in an engineering context, for example, when
asking where a signal crosses a threshold or where a force becomes zero.

## Monotonicity — does the track rise or fall?

Let us look more carefully at our straight inclined rail. The ball rolls from
left to right and its height decreases continuously. The further the ball
travels from the start, the lower it sits. This behaviour is called
**monotonicity**.

More precisely: for any two positions $x_1 < x_2$ on our track, we always find
that $h(x_1) > h(x_2)$. The height is strictly smaller at every later position.
We call this **strictly monotonically decreasing**.

Imagine now that we add a horizontal plateau to the track: the ball descends,
rolls along a flat section, and then descends again. On the flat section the
height stays constant — for any two positions $x_1 < x_2$ within the plateau
we have $h(x_1) = h(x_2)$. This means the function is no longer *strictly*
decreasing on the whole track, but it is still *monotonically decreasing* in a
broader sense, because the height never increases. We will look at this kind of
track, where different sections follow different equations, in more detail in
the next section.

We can also imagine the reverse situation: a conveyor belt that carries the ball
uphill back to the starting block. Its height function would be monotonically
increasing — the height grows as the position $x$ increases.

```{admonition} What is ... monotonicity?
:class: note
Let $f: D \to \mathbb{R}$ be a function and $I \subseteq D$ an interval.

- $f$ is **monotonically increasing** on $I$ if for all $x_1, x_2 \in I$:<br>
  $x_1 < x_2 \;\Rightarrow\; f(x_1) \leq f(x_2).$
- $f$ is **strictly monotonically increasing** on $I$ if for all $x_1, x_2 \in I$:<br>
  $x_1 < x_2 \;\Rightarrow\; f(x_1) < f(x_2).$
- $f$ is **monotonically decreasing** on $I$ if for all $x_1, x_2 \in I$:<br>
  $x_1 < x_2 \;\Rightarrow\; f(x_1) \geq f(x_2).$
- $f$ is **strictly monotonically decreasing** on $I$ if for all $x_1, x_2 \in I$:<br>
  $x_1 < x_2 \;\Rightarrow\; f(x_1) > f(x_2).$
```

Note that monotonicity always refers to a specific interval. A function can be
strictly monotonically decreasing on one part of its domain and strictly
monotonically increasing on another.

```{dropdown} Video "Math Section 12 · the monotonicity of functions" by CSCA
<iframe width="1020" height="577" src="https://www.youtube.com/embed/qQphIRsDDy4"
title="CSCA · Math Section 12·the monotonicity of functions" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Boundedness — how high and how low can it go?

Every real marble track has physical limits. The table surface prevents the ball
from going below $0~\text{cm}$, and the starting block fixes the maximum height
at $6~\text{cm}$. These physical constraints translate directly into a
mathematical property: **boundedness**.

For our height function $h(x) = -\frac{1}{4}x + 6$ on the domain
$D = [0, 24]$, we have $h(x) \geq 0$ for all $x \in D$. The table surface gives
a **lower bound** of $s = 0~\text{cm}$. Similarly, $h(x) \leq 6$ for all
$x \in D$, so the starting height gives an **upper bound** of $S = 6~\text{cm}$.
Since the function is bounded both above and below, it is simply called
**bounded**.

Not all functions behave this way. If we extended the rail infinitely far to
the right, the height would eventually become arbitrarily negative — the
function would be unbounded below. In contrast, the height could never exceed
the starting height of $6~\text{cm}$, so the function would remain bounded
above.

```{admonition} What is ... boundedness?
:class: note
A function $f: D \to \mathbb{R}$ is called

- **bounded above** if there exists a number $S$ such that $f(x) \leq S$ for
  all $x \in D$,
- **bounded below** if there exists a number $s$ such that $f(x) \geq s$ for
  all $x \in D$,
- **bounded** if it is both bounded above and bounded below.
```

## Symmetry — mirror tracks

Symmetry is everywhere in engineering. Machine parts are often designed to be
mirror-symmetric; other structures are rotationally symmetric. In mathematics
we express these symmetries through the concepts of **even** and **odd**
functions.

Imagine we extend our marble track symmetrically to the left of the starting
block: the ball can now roll either to the left or to the right, and both rails
are mirror images of each other. If we place the $y$-axis at the starting
block, the height function satisfies $h(-x) = h(x)$ for all $x$ in the domain.
For example:

\begin{equation*}
h(2) = -\frac{1}{4} \cdot 2 + 6 = 5.5~\text{cm}, \quad
h(-2) = \frac{1}{4} \cdot (-2) + 6 = 5.5~\text{cm.}
\end{equation*}

```{figure} pics/function_marble_track_symmetric.svg
---
width: 75%
name: function_marble_track_symmetric
---
Graph of the height function of a y-axis symmetric marble track.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

A marble track bounded by the table surface can never dip below zero, so we
cannot construct a point-symmetric marble track in the same way. Instead,
imagine a roller coaster built into hilly terrain: the track rises over a hill
on the right and descends into a valley of exactly the same depth on the left.
We can describe such a track by the function $h(x) = 0.1\, x^3$, where the
coordinate system is placed at the centre. Let us check the symmetry at
$x = 2$:

\begin{equation*}
h(2) = 0.1 \cdot 2^3 = 0.8~\text{cm}, \quad
h(-2) = 0.1 \cdot (-2)^3 = -0.8~\text{cm.}
\end{equation*}

In general: $h(-x) = 0.1 \cdot (-x)^3 = -0.1\, x^3 = -h(x)$. The hill on the
right corresponds to a valley of equal depth on the left — action and reaction
are equal in magnitude but opposite in direction.

```{figure} pics/function_marble_track_odd.svg
---
width: 75%
name: function_marble_track_odd
---
Graph of a roller coaster track that is point-symmetric about the origin.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

```{admonition} What is ... symmetry?
:class: note
**Even function (axis symmetry):** A function $f$ is called even if

\begin{equation*}
f(-x) = f(x) \quad \text{for all } x \in D.
\end{equation*}

Its graph is symmetric about the $y$-axis.

**Odd function (point symmetry):** A function $f$ is called odd if

\begin{equation*}
f(-x) = -f(x) \quad \text{for all } x \in D.
\end{equation*}

Its graph is point-symmetric about the origin.
```

Note that not every function is either even or odd — most functions have no
symmetry at all. Checking for symmetry is nevertheless always worthwhile, since
it can simplify calculations considerably.

```{dropdown} Video "Even and odd functions" by MatheMagician
<iframe width="1020" height="574" src="https://www.youtube.com/embed/Yx8qJ_QlHXg"
title="Even and odd functions" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Math Section 14 · parity of function" by CSCA
<iframe width="1020" height="577" src="https://www.youtube.com/embed/72SwMb5bB9U?list=PLPdlxSAWs0eJJWaOuOUq1jsA_68l7_pAF" title="CSCA · Math Section 14·parity of function"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

## Periodicity — repeating patterns

Imagine a marble track built over a series of identical hills. After each hill
the track looks exactly the same as before. If we shift the entire track
horizontally by the width of one hill, the height profile is unchanged. This
repeating structure leads us to the concept of **periodicity**.

```{figure} pics/function_marble_track_periodic.svg
---
width: 75%
name: function_marble_track_periodic
---
Graph of a periodic marble track with period $T$.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Periodic functions are particularly important in mechanical engineering:
rotating shafts, vibrating components, and alternating voltages all produce
signals that repeat themselves after a fixed time interval. We will encounter
periodic functions again in detail when we study the trigonometric functions in
chapter 4.

```{admonition} What is ... periodicity?
:class: note
A function $f$ is called **periodic** with period $T > 0$ if

\begin{equation*}
f(x + T) = f(x) \quad \text{for all } x \in D.
\end{equation*}

The smallest positive $T$ with this property is called the **fundamental
period**.
```

```{dropdown} Video "Periodic Functions" by JensenMath
<iframe width="1020" height="574" src="https://www.youtube.com/embed/oWuEVzdAF3k"
title="Periodic Functions (full lesson) | math 11 | jensenmath.ca" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Summary and outlook

We have extended the marble track to discover five key properties of functions:
zeros mark where the function value is zero; monotonicity describes whether
the function is rising or falling; boundedness tells us whether the function
values are confined within fixed limits; symmetry captures mirror or point
symmetry of the graph; and periodicity describes repeating patterns. In the
next section we look at a special class of functions where different equations
apply on different parts of the domain — the piecewise defined functions.
