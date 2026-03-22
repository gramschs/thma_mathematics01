---
authors:
  - name: Simone Gramsch
---

# Piecewise Defined Functions

So far our marble track consisted of a single straight rail, described by one
function equation across the entire domain. But what happens when we rebuild
the track with a horizontal plateau in the middle? The track now has three
clearly distinct segments, and no single equation can describe all three at
once. This leads us to a very practical class of functions: the piecewise
defined functions.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know what a **piecewise defined function** is and can read and write
  its notation.
* [ ] You can evaluate a piecewise defined function at a given point.
* [ ] You can sketch the graph of a piecewise defined function.
```

## A marble track with a plateau

Imagine we modify our marble track by inserting a horizontal plateau between
two descending sections. The ball rolls down the first rail, travels along the
flat plateau at constant height, and then descends again on a second rail to
the finishing block. The track looks like this:

```{figure} pics/fig03_marble_track_plateau.svg
---
width: 75%
name: fig03_marble_track_plateau
---
A marble track with three segments: a descending rail, a horizontal plateau,
and a second descending rail.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

To describe this track mathematically we identify three segments:

- Segment 1: from $x = 0~\text{cm}$ to $x = 8~\text{cm}$, the rail descends
  linearly with $h_1(x) = -0.25\, x + 6$,
- Segment 2: from $x = 8~\text{cm}$ to $x = 12~\text{cm}$, the plateau is
  flat with $h_2(x) = 4$,
- Segment 3: from $x = 12~\text{cm}$ to $x = 24~\text{cm}$, the rail descends
  more steeply with $h_3(x) = -\frac{1}{3}\, x + 8$.

We can verify that the segments connect continuously: at $x = 8~\text{cm}$ the
first equation gives $h_1(8) = -0.25 \cdot 8 + 6 = 4~\text{cm}$, which matches
the plateau height. At $x = 12~\text{cm}$ the third equation gives
$h_3(12) = -\frac{1}{3} \cdot 12 + 8 = 4~\text{cm}$, which also matches the
plateau.

## Definition and notation

The domain $D = [0, 24]$ is split into three sub-intervals

\begin{equation*}
I_1 = [0, 8], \quad I_2 = (8, 12], \quad I_3 = (12, 24],
\end{equation*}

and on each sub-interval a different equation applies. We write the complete
height function compactly using the **case notation**:

\begin{equation*}
h(x) = \begin{cases}
-0.25\, x + 6, & x \in [0, 8], \\
4,             & x \in (8, 12], \\
-\frac{1}{3}\, x + 8, & x \in (12, 24].
\end{cases}
\end{equation*}

This is a **piecewise defined function**. A few points are worth noting about
the notation. The sub-intervals must not overlap, and together they must cover
the entire domain. Every value of $x$ in the domain belongs to exactly one
sub-interval, so the function is still well defined in the mathematical sense:
each input has exactly one output. The boundary point $x = 8~\text{cm}$, for
instance, belongs to the closed interval $I_1 = [0, 8]$ and not to the
half-open interval $I_2 = (8, 12]$. This choice is deliberate: the parenthesis
on the left of $I_2$ means that $x = 8$ is excluded from the second segment.

## Evaluating and sketching piecewise functions

To evaluate a piecewise defined function at a given point, we first determine
which sub-interval the point belongs to, and then apply the corresponding
equation. This sounds straightforward, but it is the most common source of
errors: always check the sub-interval first.

As an example, let us evaluate the height function at three positions:

- At $x = 5~\text{cm}$: since $5 \in [0, 8]$, we use the first equation:
  $h(5) = -0.25 \cdot 5 + 6 = 4.75~\text{cm}.$
- At $x = 10~\text{cm}$: since $10 \in (8, 12]$, we use the second equation:
  $h(10) = 4~\text{cm}.$
- At $x = 18~\text{cm}$: since $18 \in (12, 24]$, we use the third equation:
  $h(18) = -\frac{1}{3} \cdot 18 + 8 = 2~\text{cm}.$

To sketch the graph, we draw each segment separately over its sub-interval and
pay careful attention to the boundary points. An open circle at a boundary
indicates that the point is excluded from that segment; a filled circle
indicates that the point is included.

```{figure} pics/fig03_function_graph_marble_track_plateau.svg
---
width: 75%
name: fig03_function_graph_marble_track_plateau
---
Graph of the piecewise defined height function of the marble track with a
plateau.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Looking back at the monotonicity from the previous section: on segment 1 the
function is strictly monotonically decreasing, on segment 2 it is constant, and
on segment 3 it is strictly monotonically decreasing again. Taken together over
the whole domain $D = [0, 24]$, the function is monotonically decreasing
(in the non-strict sense), because the height never increases.

```{dropdown} Video "Graphing a Piecewise Function" by Brian McLogan
<iframe width="1020" height="574" src="https://www.youtube.com/embed/QIG8LvPNNJQ"
title="Graphing a Piecewise Function" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Piecewise defined functions in engineering

Piecewise defined functions are not a mathematical curiosity. They appear
throughout engineering whenever a system behaves differently in different
operating regimes. A few typical examples:

- A **material under load** behaves elastically up to the yield stress and
  plastically beyond it. The stress-strain relationship is described by two
  different equations, one for each regime.
- A **control system with a threshold** responds linearly up to a saturation
  limit and then holds a constant output value. This is precisely the structure
  of our plateau track.
- An **electrical switch** is either open (current zero) or closed (current
  determined by Ohm's law), with the switching point as the boundary between two
  sub-intervals.

In each case the key question is the same as with our marble track: which
segment does the current operating point belong to?

## Summary and outlook

We have seen that a single track with multiple distinct segments requires a
piecewise defined function to describe it. The domain is split into
non-overlapping sub-intervals, each with its own equation, and boundary points
must be assigned to exactly one sub-interval. In the next section we move from
straight rails to curved ones and introduce the family of power functions and
polynomials.
