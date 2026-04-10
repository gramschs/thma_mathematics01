---
authors:
  - name: Simone Gramsch
---

# 3.5 Quadratic Functions

Among all polynomials, the quadratic function of degree 2 deserves its own
section. Its graph is a parabola, a curve that appears throughout engineering
in contexts ranging from projectile trajectories to the cross-sections of
parabolic reflectors. More importantly for us, the parabola has a lowest or
highest point, called the vertex, that will become the central object of study
when we reach differential calculus. In this section we develop all the tools
needed to work with quadratic functions confidently.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know the **standard form** $f(x) = ax^2 + bx + c$ and the
  **vertex form** $f(x) = a(x - x_V)^2 + y_V$ of a quadratic function and
  can convert between them.
* [ ] You can identify the **vertex** $V = (x_V, y_V)$ of a parabola and
  compute it from the standard form.
* [ ] You can determine whether a parabola opens upwards or downwards from
  the sign of the leading coefficient $a$.
* [ ] You can compute the zeros of a quadratic function using the
  **pq-formula** or the **abc-formula**.
* [ ] You know the **discriminant** and can use it to determine the number of
  real zeros.
* [ ] You can sketch a parabola from its key features.
```

## A parabolic rail profile

Imagine we replace the straight inclined rail of our marble track with a
curved one that dips into a valley. The rail descends from the starting block,
reaches its lowest point somewhere in the middle, and then rises again toward
the finishing block. If we place the coordinate origin at the starting block as
before, the height function of such a rail might look like this:

\begin{equation*}
h(x) = 0.01x^2 - 0.5x + 6.
\end{equation*}

Here $h$ is measured in centimetres and $x$ runs from $0$ to $50~\text{cm}$.
At $x = 0$ we have $h(0) = 6~\text{cm}$, the starting height. The rail dips
down, reaches its lowest point, and then climbs back up. The graph of this
function is a **parabola** opening upward, since the coefficient of $x^2$ is
positive.

```{figure} pics/fig03_marble_track_parabola.svg
---
width: 75%
name: fig03_marble_track_parabola
---
A marble track with a parabolic rail profile. The lowest point of the rail is
the vertex of the parabola.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

A quadratic function of this form, a sum of a degree-2 power function, a
linear term, and a constant, is the general shape we want to study.

```{admonition} What is ... a quadratic function?
:class: note
A **quadratic function** is a function of the form

\begin{equation*}
f(x) = ax^2 + bx + c,
\end{equation*}

where $a$, $b$, and $c$ are real numbers and $a \neq 0$. This representation
is called the **standard form**. The coefficient $a$ is the **leading
coefficient**.
```

The leading coefficient $a$ determines the opening direction of the parabola:
if $a > 0$ the parabola opens upward and has a lowest point; if $a < 0$ it
opens downward and has a highest point. The larger $|a|$ is, the narrower the
parabola.

```{dropdown} Video "Quadratic Functions" by StudyPug
<iframe width="1020" height="574" src="https://www.youtube.com/embed/KRwb4YhQPwA"
title="Quadratic Functions - Explained, Simplified and Made Easy" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Standard form and vertex form

The standard form $f(x) = ax^2 + bx + c$ is convenient for reading off the
$y$-intercept directly: setting $x = 0$ gives $f(0) = c$. However, it does not
immediately reveal the most important geometric feature of the parabola: its
vertex.

The **vertex** $V = (x_V, y_V)$ is the lowest point of an upward-opening
parabola or the highest point of a downward-opening one. It is the point where
the parabola changes from decreasing to increasing (or vice versa). We can
compute the $x$-coordinate of the vertex from the standard form by completing
the square, which gives:

\begin{equation*}
x_V = -\frac{b}{2a}.
\end{equation*}

Once we know $x_V$, the $y$-coordinate follows by substitution:

\begin{equation*}
y_V = f(x_V) = a x_V^2 + b x_V + c.
\end{equation*}

For our parabolic rail $h(x) = 0.01x^2 - 0.5x + 6$ we obtain:

\begin{equation*}
x_V = -\frac{-0.5}{2 \cdot 0.01} = \frac{0.5}{0.02} = 25~\text{cm},
\end{equation*}

\begin{equation*}
y_V = 0.01 \cdot 25^2 - 0.5 \cdot 25 + 6 = 6.25 - 12.5 + 6 = -0.25~\text{cm}.
\end{equation*}

The lowest point of the rail lies at $x = 25~\text{cm}$, at a height of
$-0.25~\text{cm}$, that is, just below the table surface. Knowing the vertex,
we can write the height function in the alternative **vertex form**:

\begin{equation*}
h(x) = a(x - x_V)^2 + y_V = 0.01(x - 25)^2 - 0.25.
\end{equation*}

```{admonition} What is ... the vertex form?
:class: note
The **vertex form** of a quadratic function is

\begin{equation*}
f(x) = a(x - x_V)^2 + y_V,
\end{equation*}

where $V = (x_V, y_V)$ is the vertex of the parabola and $a$ is the leading
coefficient. The vertex form makes the position of the vertex immediately
visible.
```

Both forms describe exactly the same function. The standard form is convenient
for calculations involving individual coefficients; the vertex form is
convenient whenever the vertex itself is the quantity of interest.

```{dropdown} Video "Standard form to vertex form" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/pf9LkX8hpTQ"
title="Standard Form to Vertex Form - Quadratic Equations" frameborder="0" allow="accelerometer;
autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zeros and the discriminant

*Where does the parabolic rail cross the table surface?* This is the question
about the zeros of the height function, that is, the values of $x$ for which
$h(x) = 0$. For our rail, a zero corresponds to a point where the ball is
exactly at table height, which is physically the point where it either leaves
or re-enters the table surface.

For a quadratic function in the special form $f(x) = x^2 + px + q$ (that is,
with leading coefficient $a = 1$), we use the **pq-formula**:

\begin{equation*}
x_{1,2} = -\frac{p}{2} \pm \sqrt{\left(\frac{p}{2}\right)^2 - q}.
\end{equation*}

For the general standard form $f(x) = ax^2 + bx + c$ with arbitrary $a \neq 0$,
we use the **quadratic formula**:

\begin{equation*}
x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}.
\end{equation*}

Both formulas are equivalent: dividing the standard form through by $a$ and
setting $p = b/a$ and $q = c/a$ converts one into the other.

The expression under the square root is called the **discriminant**. For the
quadratic formula it is $\Delta = b^2 - 4ac$, and it tells us immediately how
many real zeros the quadratic function has:

- $\Delta > 0$: two distinct real zeros (the parabola crosses the $x$-axis twice).
- $\Delta = 0$: exactly one real zero (the parabola touches the $x$-axis at the vertex).
- $\Delta < 0$: no real zeros (the parabola lies entirely above or below the $x$-axis).

The case $\Delta = 0$ has a neat geometric interpretation: the vertex lies
exactly on the $x$-axis, so $y_V = 0$.

Let us apply this to our parabolic rail $h(x) = 0.01x^2 - 0.5x + 6$. We
compute the discriminant:

\begin{equation*}
\Delta = (-0.5)^2 - 4 \cdot 0.01 \cdot 6 = 0.25 - 0.24 = 0.01 > 0.
\end{equation*}

Since $\Delta > 0$, there are two zeros. Using the quadratic formula:

\begin{equation*}
x_{1,2} = \frac{0.5 \pm \sqrt{0.01}}{2 \cdot 0.01} = \frac{0.5 \pm 0.1}{0.02},
\end{equation*}

which gives $x_1 = 30~\text{cm}$ and $x_2 = 20~\text{cm}$. The rail crosses
the table surface at two positions, consistent with the vertex being just below
the surface at $y_S = -0.25~\text{cm}$.

## Sketching a parabola

With the tools developed above we can sketch any parabola quickly and
accurately. We proceed in four steps:

1. **Opening direction**: check the sign of $a$. If $a > 0$, the parabola
   opens upward; if $a < 0$, it opens downward.
2. **Vertex**: compute $x_V = -b/(2a)$ and $y_V = f(x_V)$. Mark the vertex
   $V = (x_V, y_V)$ in the coordinate system.
3. **Zeros**: compute the discriminant $\Delta = b^2 - 4ac$. If $\Delta > 0$,
   compute and mark both zeros using the quadratic formula. If $\Delta = 0$, the
   single zero is the $x$-coordinate of the vertex. If $\Delta < 0$, there
   are no zeros to mark.
4. **$y$-intercept**: compute $f(0) = c$ and mark the point $(0, c)$.

These four pieces of information are sufficient for a qualitatively correct
sketch. A smooth curve through the vertex, symmetric about the vertical line
$x = x_V$, connecting the zeros and the $y$-intercept, completes the drawing.

```{figure} pics/fig03_parabola_sketch.svg
---
width: 75%
name: fig03_parabola_sketch
---
Key features of a parabola: opening direction, vertex, zeros, and $y$-intercept.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

```{dropdown} Video "Graphing Quadratic Functions" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/Hq2Up_1Ih5E"
title="Graphing Quadratic Functions in Vertex &amp; Standard Form - Axis of Symmetry - Word Problems" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## The vertex and differential calculus

We have seen that the vertex is the point where the parabola transitions from
decreasing to increasing or vice versa. At that point the rail is neither
rising nor falling: its steepness is momentarily zero. In the language of
differential calculus, the **derivative** of the function is zero at the
vertex.

This observation is not specific to parabolas. For any differentiable function,
the points where the derivative is zero are candidates for local minima and
maxima. Finding these points is one of the central tasks of differential
calculus, and the vertex of a parabola is the simplest possible example. We
will return to this idea in detail in a later chapter.

## Summary and outlook

The quadratic function has two equivalent representations: the standard form,
which shows the $y$-intercept directly, and the vertex form, which shows the
vertex directly. The discriminant determines the number of real zeros. Taken
together, the opening direction, vertex, zeros, and $y$-intercept are
sufficient to sketch any parabola. In the next section we look at the
composition of functions, a construction that will later become the foundation
of the chain rule in differential calculus.
