---
authors:
  - name: Simone Gramsch
---

# 3.1 What is a Function?

The height of a ball rolling along a marble track -- how can we describe this
mathematically? This seemingly simple question leads us directly to one of the
most important concepts in mathematics: the concept of a function. In this
section we develop the necessary mathematical tools using a marble track as our
guiding example.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know how a **function** is defined in mathematics.
* [ ] You can determine the **domain** and the **codomain** of a function.
* [ ] You can determine the **image** of a function.
* [ ] You are familiar with the three representations of a function:
  **table of values**, **function formula**, and **function graph**.
```

## What is a function?

Imagine we have set up a simple marble track. There is a starting block, a
straight inclined rail, and a finishing block that acts as a catch container.
Our central question is: *How high is the ball at every position along the
track?*

```{figure} pics/kugelbahn_gerade_w800px.png
---
width: 75%
name: marble_track_straight
---
A straight inclined marble track.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

To describe the height mathematically, we need a coordinate system. We choose
the straight line through the starting block and the finishing block as the
first axis. This line lies on the table surface. As the second axis we choose
the height above the table surface, pointing vertically upward. We are free to
place the origin wherever we like -- we choose the position of the starting
block on the table surface as the origin $O$.

With this coordinate system we can describe the position of the ball precisely.
We measure its distance from the origin along the first axis and call this
position $x$. We call the height above the table surface $h$.

Now we can assign to every position $x$ exactly one height $h$. The word
*exactly one* is crucial here: there is no position along the track where the
ball could be at two different heights at the same time. We can measure the
height at several positions and record the results in a table:

| Position $x$ [cm] | Height $h$ [cm] |
| ------------------ | --------------- |
| 0.0 | 6.0 |
| 4.8 | 4.8 |
| 9.6 | 3.6 |
| 14.4 | 2.4 |
| 19.2 | 1.2 |
| 24.0 | 0.0 |

We have not measured the height at every possible position, but we could.
Even at intermediate positions such as $x = 0.567~\text{cm}$ or
$x = 17.9~\text{cm}$ we could measure the corresponding height.

This unique assignment between position and height is the essence of a
mathematical function. In mathematics, such a unique assignment between two
sets is called a **function**. We define it formally as follows:

```{admonition} What is ... a function?
:class: note
A **function** is a unique assignment between two sets. Each element of the
first set (the domain) is assigned exactly one element of the second set (the
codomain).
```

If we abbreviate the domain as $D$, the codomain as $W$, and the function as
$f$, we can write this definition compactly as:

\begin{equation*}
f: D \to W, \quad x \mapsto f(x).
\end{equation*}

The element of the codomain that is assigned to the element $x$ of the domain
is called the **function value** and is written as $f(x)$.

## How can we represent a function?

For our marble track height function there are several ways of giving a
mathematical description. Each has its own advantages.

The simplest representation is the **table of values**. It is particularly
useful when the function is determined by measurement. We have already created
such a table above with our marble track measurements. A table of values is
ideal for experimental data.

In the case of our marble track we can also describe the height of the ball
mathematically in a compact and exact form:

\begin{equation*}
h(x) = -\frac{1}{4} x + 6.
\end{equation*}

Here $h(x)$ gives the height at position $x$, measured in centimetres. We now
have an exact formula that allows us to calculate the height at any position.
This representation is called the **function formula**. It is precise, compact,
and ideal for further calculations.

A third representation is the **function graph** or **plot**. The function
graph corresponds to the side view of our marble track. For each $x$-value we
compute the corresponding function value $h(x)$, usually abbreviated as $y$,
and draw the point $(x, y)$ in an $xy$-coordinate system.

```{figure} pics/function_marble_track.svg
---
width: 75%
name: function_marble_track
---
Graph of the height function of the ball on the marble track.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

The graph makes the behaviour of the function immediately visible and is
particularly useful for building intuition. All three representations describe
the same function — just in different ways.

```{dropdown} Video "What is a function?" by MatheMagician
<iframe width="1020" height="574" src="https://www.youtube.com/embed/FM4jsBGZKi4?list=PLJMXXdEk8kMD27qyxFL_d7Slkk0NpBAlh" title="What is a function?" frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; 
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "An example of a function" by MatheMagician
<iframe width="1020" height="574" src="https://www.youtube.com/embed/TocYv-mpKks?list=PLJMXXdEk8kMD27qyxFL_d7Slkk0NpBAlh" title="An example of a function" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; 
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Function Notation" by Khan Academy
<iframe width="560" height="315" src="https://www.youtube.com/embed/kvGsIo1TmsM"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen></iframe>
```

```{dropdown} Video "Math Section 9 · the concept of function" by CSCA
<iframe width="1020" height="577" src="https://www.youtube.com/embed/YvT5LdaUrU0?list=PLPdlxSAWs0eJJWaOuOUq1jsA_68l7_pAF" title="CSCA · Math  Section 9·the concept of function" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Math Section 10·representation of function" by CSCA
<iframe width="1020" height="577" src="https://www.youtube.com/embed/W8_bv7fMqdc?list=PLPdlxSAWs0eJJWaOuOUq1jsA_68l7_pAF" title="CSCA · Math Section 10·representation of function" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Domain, codomain, and range

Our marble track is not infinitely long, and the possible height values are
limited. These physical constraints lead us to two important mathematical
concepts.

Not all positions $x$ are meaningful. Positions to the left of the starting
block ($x < 0~\text{cm}$) and to the right of the finishing block
($x > 24~\text{cm}$) are not relevant. We therefore consider only the interval:

\begin{equation*}
X = [0, 24] \quad \text{measured in cm.}
\end{equation*}

The set of all valid input values is called the **domain** of the function.

For the height values we use real numbers. So the possible output of the
function is the so-called **codomain** $Y = \mathbb{R}$. But we notice that the
ball starts at $6~\text{cm}$ and ends at $0~\text{cm}$. So the height function
takes values in the interval

\begin{equation*}
f(X) = [0, 6] \quad \text{measured in cm},
\end{equation*}

which is called the **range** of the function $f$.

```{admonition} What is ... the domain, codomain, and range?
:class: note
**Domain $X$:** The set of all valid input values ($x$-values) for which the
function is defined.

**Codomain $Y$:** The set into which the function maps. It contains all
possible output values, but not every value in $Y$ must actually be reached.

**Range $f(X)$:** The set of all output values that the function
actually takes. For our marble track, we have $f(X) = [0, 6]$.
```

The domain defines the **validity range** of the function. Outside the domain
our formula $h(x) = -\frac{1}{4}x + 6$ produces a number, but it has no
physical meaning — at $x = -10~\text{cm}$ the formula would give a height of
$8.5~\text{cm}$, but there is no rail there. Extrapolation, that is, applying
a formula outside its domain, is a common source of errors in engineering: a
formula is only valid within its domain.

The image tells us which heights the ball can actually reach on our track. This
matters in practice: where does the catch container need to be placed? Could we
extend the range of heights by redesigning the track?

```{dropdown} Video "Domain, codomain and range of a function" by MatheMagician
<iframe width="1020" height="574" src="https://www.youtube.com/embed/uX7viLCY878?list=PLJMXXdEk8kMD27qyxFL_d7Slkk0NpBAlh" title="Domain, codomain and range of a function"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

```{dropdown} Video "Domain, Codomain, and Range" by Center of Math
<iframe width="1020" height="574" src="https://www.youtube.com/embed/aQizbVOjrJE"
title="Domain, Codomain, and Range (Correction)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Summary and outlook

Using a simple marble track we have developed the foundations of functions: a
function is a unique assignment between an input value and an output value,
which we can represent as a table of values, a function formula, or a function
graph. The domain and image define the validity range and the set of reachable
values of our mathematical description. Our straight inclined rail is only the
beginning. In the next section we extend the marble track system to discover
important properties that functions can have.
