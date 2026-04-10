---
authors:
  - name: Simone Gramsch
---

# 5.1 The Difference Quotient

In chapters 3 and 4 we built a toolkit for describing how quantities depend on
each other. We assigned to every position on the marble track a height, to
every angle a sine value, to every time a voltage. But knowing the value of a
function at each point is only half of the picture. In engineering we
constantly ask a second, equally important question: *how quickly does the
quantity change?* A rail that drops steeply at the start and then flattens out
behaves very differently from one that descends at a constant rate, even if
both begin and end at the same heights. To capture this idea of rate of change
precisely, we introduce the difference quotient.

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **difference quotient**
  \begin{equation*}
  \dfrac{f(x_0 + h) - f(x_0)}{h}
  \end{equation*}
  and can compute it for a given function
  and a given point $x_0$.
* [ ] You can interpret the difference quotient as the **average rate of
  change** of a function over the interval $[x_0,\, x_0 + h]$.
* [ ] You understand the geometric meaning of the difference quotient as the
  slope of the **secant line** through the two points $(x_0, f(x_0))$ and
  $(x_0 + h, f(x_0 + h))$ on the graph.
```

## How steeply does the rail descend between two points?

In section 3.5 we studied parabolic marble tracks. We now work with the
following configuration, which keeps the rail comfortably above the table
surface throughout its domain. We write the height function as $f(x)$ so that
the letter $h$ remains free for its standard role as the step size in the
difference quotient:

\begin{equation*}
f(x) = 0.02\,x^2 - 0.6\,x + 6, \quad x \in [0, 30],
\end{equation*}

where $x$ is the position along the track in centimetres and $f(x)$ is the
height above the table surface in centimetres.

```{figure} pics/fig05_marble_track_parabola.svg
Graph of the height function $f(x) = 0.02x^2 - 0.6x + 6$ of the parabolic marble track on the domain $[0, 30]$.
(Source: own figure; licence [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

The rail starts at $f(0) = 6~\text{cm}$, descends to its lowest point at $x =
15~\text{cm}$ with $f(15) = 1.5~\text{cm}$, and then rises symmetrically back to
$f(30) = 6~\text{cm}$ at the finishing block. Unlike the straight rail from
section 3.1, this track does not descend at the same rate everywhere. Near the
starting block the rail falls steeply; near the bottom of the valley it is
almost flat; beyond the vertex it begins to climb.

*How can we describe this varying steepness numerically?* The simplest approach
is to pick two positions on the track, measure the heights at both, and compute
the average rate of change between them. Suppose we choose position
$x_0 = 5~\text{cm}$ and position $x_1 = 20~\text{cm}$.

```{figure} pics/fig05_marble_track_difference_quotient.svg
Graph of the height function with the secant line through $P_1 = (5, 3.5)$ and $P_2 = (20, 2)$, showing the rise $\Delta f$ and the run $\Delta x$.
(Source: own figure; licence [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

The heights are

\begin{equation*}
f(5) = 0.02 \cdot 25 - 0.6 \cdot 5 + 6 = 0.5 - 3 + 6 = 3.5~\text{cm},
\end{equation*}

\begin{equation*}
f(20) = 0.02 \cdot 400 - 0.6 \cdot 20 + 6 = 8 - 12 + 6 = 2~\text{cm}.
\end{equation*}

Over this stretch the track drops by $1.5~\text{cm}$ while advancing
$15~\text{cm}$ horizontally. The average rate of change is

\begin{equation*}
\frac{f(20) - f(5)}{20 - 5} = \frac{2 - 3.5}{15} = \frac{-1.5}{15} = -0.1~\frac{\text{cm}}{\text{cm}}.
\end{equation*}

The negative sign reflects the downward trend. The magnitude $0.1$ tells us
that the track drops, on average, $0.1~\text{cm}$ for every centimetre of
horizontal travel over this interval.

## What is the difference quotient?

The calculation above works for any two positions, not just the ones we chose.
If we take a fixed reference point $x_0$ and a second point at distance $h$
from it, so that the second position is $x_0 + h$, then the average rate of
change between the two points is

\begin{equation*}
\frac{f(x_0 + h) - f(x_0)}{h}.
\end{equation*}

The numerator is the change in height, the denominator is the change in
position, and the quotient is the average slope of the track over the
interval $[x_0,\, x_0 + h]$.

This ratio is called the **difference quotient** of the function $f$ at the
point $x_0$ with step size $h$. The name is straightforward: the numerator is a
difference, the denominator is a difference, and we divide one by the other.

```{admonition} What is ... the difference quotient?
:class: note
Let $f$ be a function defined on an interval that contains both $x_0$ and
$x_0 + h$. The **difference quotient** of $f$ at the point $x_0$ with step
size $h \neq 0$ is

\begin{equation*}
\frac{f(x_0 + h) - f(x_0)}{h}.
\end{equation*}

It measures the average rate of change of $f$ over the interval
$[x_0,\, x_0 + h]$.
```

Let us apply the definition to our parabolic track at $x_0 = 5~\text{cm}$ with
several step sizes. For $h = 15~\text{cm}$ we already found the value $-0.1$.
For a shorter step $h = 5~\text{cm}$ we get

\begin{equation*}
\frac{f(10) - f(5)}{5} = \frac{(0.02 \cdot 100 - 0.6 \cdot 10 + 6) - 3.5}{5}
= \frac{2 - 3.5}{5} = \frac{-1.5}{5} = -0.3.
\end{equation*}

For an even shorter step $h = 1~\text{cm}$ we get

\begin{equation*}
\frac{f(6) - f(5)}{1} = (0.02 \cdot 36 - 0.6 \cdot 6 + 6) - 3.5
= 3.12 - 3.5 = -0.38.
\end{equation*}

The three values, $-0.1$, $-0.3$, and $-0.38$, are all different. This is
expected: each one describes the average steepness over a different stretch of
track, and our parabola is not equally steep everywhere. As the step size
shrinks, we zoom in closer and closer to the point $x_0 = 5$. The values appear
to be approaching a limiting number. What that limit is, and what it means, is
the subject of the next section.

<!--
  SVELTE APP 1: "Difference quotient explorer"
  
  An interactive plot of the parabolic marble track f(x) = 0.02x² - 0.6x + 6
  on the domain [0, 30].
  
  Controls:
    - A slider for x0 (the fixed base point), range [0, 25], default 5.
    - A slider for h (the step size), range [0.5, 15], default 10.
  
  Display:
    - The parabola in dark blue.
    - Two filled dots at (x0, f(x0)) and (x0+h, f(x0+h)), labelled P1 and P2.
    - A shaded rectangle on the x-axis showing the interval [x0, x0+h],
      labelled Δx = h.
    - A vertical arrow from f(x0) to f(x0+h) at position x0+h,
      labelled Δf = f(x0+h) - f(x0).
    - The secant line through P1 and P2, extended across the full plot.
  
  Info tiles below the chart:
    - "Δx" showing the step size h.
    - "Δf" showing f(x0+h) - f(x0), rounded to 3 decimal places.
    - "Difference quotient Δf/Δx" showing the computed value, rounded to 3
      decimal places, colored red for negative and green for positive.
  
  Purpose: students can drag both sliders and watch the secant line tilt and
  the difference quotient update, building intuition that the difference
  quotient captures the average steepness of the track between two points.
-->

## What does the difference quotient look like geometrically?

There is a clean geometric picture that makes the difference quotient
immediately visible. Consider the graph of the height function, the parabola
we drew in section 3.5. The two points $P_1 = (x_0,\, f(x_0))$ and
$P_2 = (x_0 + h,\, f(x_0 + h))$ both lie on this curve. Draw the straight
line that passes through both of them. This line is called the **secant line**
through $P_1$ and $P_2$.

The slope of the secant line is, by definition, the rise divided by the run:

\begin{equation*}
m = \frac{\Delta f}{\Delta x} = \frac{f(x_0 + h) - f(x_0)}{h}.
\end{equation*}

This is exactly the difference quotient. So the difference quotient has a
direct visual meaning: it is the slope of the secant line connecting the two
chosen points on the curve.

For our three examples at $x_0 = 5$, the secant lines have slopes $-0.1$,
$-0.3$, and $-0.38$. As $h$ decreases, the point $P_2$ slides along the
parabola toward $P_1$. The secant line rotates and its slope changes. What
happens in the limit as $P_2$ approaches $P_1$ and the secant becomes a line
that just touches the curve at a single point? That limiting line is the tangent
to the curve at $P_1$, and finding it is the central goal of differential
calculus.

<!--
  SVELTE APP 2: "Secant approaches tangent" (= the existing App.svelte)
  
  Adapt the function to the marble track: f(x) = 0.02x² - 0.6x + 6,
  domain [0, 30]. Fix x0 = 5, slider range for h: [0.01, 10], default h = 5.
  Analytical derivative: f'(x) = 0.04x - 0.6, so f'(5) = -0.4.
  
  The app already shows:
    - The function curve (dark blue).
    - The secant through P1 and P2 (red), updating live with the slider.
    - The tangent at x0 (green dashed), shown as a preview.
    - Info tiles: secant slope, approximation error |Δf/Δx - f'(x0)|,
      colored from red (large error) to green (small error).
  
  Purpose: the visual appearance of the secant rotating toward the tangent
  as h → 0 prepares students for the key concept of section 5.2, the
  differential quotient. The error tile gives a first hint that the secant
  is only an approximation, and that a better description of local steepness
  is possible.
  
  Note for the instructor: tell students to observe that the error tile turns
  green as h → 0. Section 5.2 explains why.
-->

## Where does the difference quotient appear in engineering?

The difference quotient is not an abstract construction. It arises naturally
wherever we measure how fast something changes between two observable moments.

In structural engineering, the deflection of a beam under load varies along its
length. If we measure the deflection at two points separated by a distance $h$,
the difference quotient gives the average slope of the deflected beam over that
span. This slope determines the bending stress, which is the quantity the
engineer checks against the material's yield strength.

In thermal engineering, the temperature inside a wall varies with depth.
Measuring the temperature at two positions gives the average temperature
gradient via the difference quotient, and that gradient drives the heat flux
through the wall by Fourier's law.

In each case the formula is the same: take two measurements, subtract, divide
by the separation. The difference quotient is, in this sense, the mathematical
formalization of what an engineer already does when reading two sensor values
and asking how quickly the quantity is changing between them.

## Additional Learning Material

```{dropdown} Video "Difference quotient" by Mario's Math Tutoring
<iframe width="1020" height="574" src="https://www.youtube.com/embed/L_GApcZZgsE"
title="Difference Quotient - What is it? (PreCalculus)" frameborder="0" allow="accelerometer;
autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Difference Quotient" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/qQgVomi8lCc"
title="Difference Quotient" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "How to Compute the Difference Quotient (f(x + h) - f(x))/h" by The Math Sorcerer
<iframe width="1020" height="553" src="https://www.youtube.com/embed/GEJ4YqFK5CM"
title="How to Compute the Difference Quotient (f(x + h) - f(x))/h" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Summary and outlook

We have introduced the difference quotient as a precise mathematical tool for
measuring the average rate of change of a function over a finite interval. For
the parabolic marble track, the difference quotient at $x_0 = 5~\text{cm}$
produces values $-0.1$, $-0.3$, and $-0.38$ for decreasing step sizes, and
those values approach a limit as $h$ shrinks toward zero. The geometric picture is equally
clear: the difference quotient is the slope of the secant line through two
points on the graph, and as the step size decreases, that secant line rotates
toward the tangent. What the tangent line is, how its slope is defined
rigorously, and why that slope is the right notion of instantaneous steepness
are the questions we take up in the next section.
