---
authors:
  - name: Simone Gramsch
---

# Trigonometric Functions

A crankshaft rotates, a piston oscillates, a bridge vibrates under traffic
load, an alternating voltage drives a motor. Periodic phenomena are everywhere
in mechanical engineering, and the mathematical tool for describing all of them
is the same: the trigonometric functions. In this section we build these
functions from the ground up, starting from the right-angled triangle and
extending to the unit circle so that every angle, positive, negative, or
larger than a full turn, is covered.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know how **sine**, **cosine**, and **tangent** are defined in the
  right-angled triangle using opposite side, adjacent side, and hypotenuse.
* [ ] You can read off the values of sine and cosine on the **unit circle** for
  standard angles and know how to convert between degrees and radians.
* [ ] You know the key properties of sine and cosine: domain, range,
  period $2\pi$, symmetry, zeros, maxima, and minima.
* [ ] You know the properties of the **tangent**: domain, range, period
  $\pi$, zeros, and vertical asymptotes.
* [ ] You can interpret the parameters of the general sinusoidal form
  $f(t) = A \sin(\omega t + \varphi) + d$ in an engineering context.
```

## Trigonometric functions in the right-angled triangle

Imagine a connecting rod in an engine. One end is fixed at the crankshaft
center and the other traces a circular path. To find the horizontal and
vertical components of the rod's position at a given angle, we decompose its
length into two perpendicular directions. This decomposition is exactly what
sine and cosine do.

Consider a right-angled triangle with an acute angle $\alpha$ at one corner.
The three sides of the triangle are named relative to the angle $\alpha$:

- the **opposite side** is the side across from $\alpha$,
- the **adjacent side** is the side that forms one of the two legs of $\alpha$,
- the **hypotenuse** is the longest side, opposite the right angle.

```{figure} pics/fig04_right_triangle.svg
---
width: 60%
name: fig04_right_triangle
---
A right-angled triangle with angle $\alpha$, opposite side $a$, adjacent side
$b$, and hypotenuse $c$.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

We define the three basic trigonometric functions by the ratios of these sides:

\begin{equation*}
\sin(\alpha) = \frac{\text{opposite}}{\text{hypotenuse}}, \quad
\cos(\alpha) = \frac{\text{adjacent}}{\text{hypotenuse}}, \quad
\tan(\alpha) = \frac{\text{opposite}}{\text{adjacent}}.
\end{equation*}

For the connecting rod of length $r$ at angle $\alpha$, the horizontal
component of its tip is $r \cos(\alpha)$ and the vertical component is
$r \sin(\alpha)$. Sine and cosine decompose a length into its components along
two perpendicular directions.

This triangle-based definition has one limitation: it only works for angles
between $0°$ and $90°$, since a right-angled triangle cannot contain an angle
greater than $90°$. To describe a full rotation of the crankshaft, including
angles beyond $90°$ and even multiple complete turns, we need a broader
definition.

## The unit circle

We extend the definition of sine and cosine to all angles using the
**unit circle**, a circle of radius 1 centered at the origin. For any angle
$\alpha$, we place the angle at the origin with one ray along the positive
$x$-axis and measure $\alpha$ counterclockwise. The point where the other ray
meets the unit circle has coordinates $(\cos(\alpha), \sin(\alpha))$.

```{figure} pics/fig04_unit_circle.svg
---
width: 75%
name: fig04_unit_circle
---
The unit circle. For any angle $\alpha$, the point on the circle has
$x$-coordinate $\cos(\alpha)$ and $y$-coordinate $\sin(\alpha)$.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

This definition agrees with the triangle definition for $0 < \alpha < 90°$ and
extends it naturally to all other angles. A negative angle is measured
clockwise. An angle greater than $360°$ simply means more than one full
rotation and gives the same point on the circle as the corresponding angle
reduced by the appropriate multiple of $360°$.

**Degrees and radians.** In the triangle definition, angles are naturally
measured in degrees. In calculus and most engineering formulas, angles are
measured in **radians**. One full rotation is $2\pi$ radians, so $180° = \pi$
radians. The conversion formulas are:

\begin{equation*}
\alpha_{\text{rad}} = \frac{\pi}{180°} \cdot \alpha_{\text{deg}}, \qquad
\alpha_{\text{deg}} = \frac{180°}{\pi} \cdot \alpha_{\text{rad}}.
\end{equation*}

From here on we use radians exclusively.

**Standard values.** We can read off the sine and cosine of several standard
angles directly from the unit circle. The most important ones are collected in
the following table:

| $\alpha$ | $0$ | $\dfrac{\pi}{6}$ | $\dfrac{\pi}{4}$ | $\dfrac{\pi}{3}$ | $\dfrac{\pi}{2}$ |
| -------- | --- | --------------- | --------------- | --------------- | --------------- |
| $\sin(\alpha)$ | $0$ | $\dfrac{1}{2}$ | $\dfrac{\sqrt{2}}{2}$ | $\dfrac{\sqrt{3}}{2}$ | $1$ |
| $\cos(\alpha)$ | $1$ | $\dfrac{\sqrt{3}}{2}$ | $\dfrac{\sqrt{2}}{2}$ | $\dfrac{1}{2}$ | $0$ |

The values for angles in the other three quadrants follow by symmetry, which
we will discuss in the next subsection.

## Properties of sine and cosine

With the unit circle definition in hand, we can determine all the key
properties of sine and cosine.

**Domain and range.** Every angle $\alpha \in \mathbb{R}$ corresponds to a
point on the unit circle, so the domain of both sine and cosine is $\mathbb{R}$.
The coordinates of any point on the unit circle lie between $-1$ and $1$, so
the range of both functions is $[-1, 1]$.

**Period.** Adding $2\pi$ to an angle returns to the same point on the unit
circle: $\sin(\alpha + 2\pi) = \sin(\alpha)$ and
$\cos(\alpha + 2\pi) = \cos(\alpha)$. Both functions are periodic with period
$T = 2\pi$, and $2\pi$ is the fundamental period.

**Symmetry.** Cosine is an even function: $\cos(-\alpha) = \cos(\alpha)$.
Geometrically, reflecting an angle about the $x$-axis does not change the
$x$-coordinate of the corresponding unit circle point. Sine is an odd
function: $\sin(-\alpha) = -\sin(\alpha)$. Reflecting about the $x$-axis
changes the sign of the $y$-coordinate.

**Zeros, maxima, and minima.** The zeros of sine are at $\alpha = k\pi$ for
any integer $k$. Its maxima of value $1$ occur at $\alpha = \pi/2 + 2k\pi$
and its minima of value $-1$ at $\alpha = -\pi/2 + 2k\pi$. The zeros of
cosine are at $\alpha = \pi/2 + k\pi$. Its maxima of value $1$ occur at
$\alpha = 2k\pi$ and its minima of value $-1$ at $\alpha = \pi + 2k\pi$.

```{figure} pics/fig04_sine_cosine_graphs.svg
---
width: 75%
name: fig04_sine_cosine_graphs
---
Graphs of $\sin(\alpha)$ (blue) and $\cos(\alpha)$ (orange) over two full
periods. Note that the cosine graph is the sine graph shifted to the left by
$\pi/2$.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## The tangent

The tangent is defined as the ratio of sine to cosine:

\begin{equation*}
\tan(\alpha) = \frac{\sin(\alpha)}{\cos(\alpha)}.
\end{equation*}

This is consistent with the triangle definition:

\begin{equation*}
\frac{\sin(\alpha)}{\cos(\alpha)} =
\frac{(\text{opposite}/\text{hypotenuse})}{(\text{adjacent}/\text{hypotenuse})} =
\frac{\text{opposite}}{\text{adjacent}}.
\end{equation*}

**Domain.** Since the denominator $\cos(\alpha)$ is zero at
$\alpha = \pi/2 + k\pi$ for integer $k$, the tangent is not defined at these
points. The domain is $\mathbb{R} \setminus \{\pi/2 + k\pi \mid k \in \mathbb{Z}\}$.

**Range.** As $\alpha$ approaches $\pi/2$ from below, $\cos(\alpha)$
approaches zero from above while $\sin(\alpha)$ approaches $1$, so
$\tan(\alpha) \to +\infty$. Approaching $\pi/2$ from above gives
$\tan(\alpha) \to -\infty$. The tangent therefore takes all real values:
range $\mathbb{R}$.

**Period.** Since $\sin(\alpha + \pi) = -\sin(\alpha)$ and
$\cos(\alpha + \pi) = -\cos(\alpha)$, their ratio satisfies
$\tan(\alpha + \pi) = \tan(\alpha)$. The tangent has period $\pi$, half the
period of sine and cosine.

**Zeros and asymptotes.** The tangent is zero wherever sine is zero: at
$\alpha = k\pi$. The vertical asymptotes occur at $\alpha = \pi/2 + k\pi$,
the points excluded from the domain.

```{figure} pics/fig04_tangent_graph.svg
---
width: 75%
name: fig04_tangent_graph
---
Graph of $\tan(\alpha)$ over two periods. Vertical asymptotes occur at
$\alpha = \pm\pi/2$ and $\alpha = \pm 3\pi/2$.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## The general sinusoidal form

In engineering applications, the oscillation we want to describe is rarely a
pure sine with amplitude 1 and no phase offset. An alternating voltage, for
instance, has a specific amplitude, a specific frequency, and a specific phase
relative to some reference signal. The **general sinusoidal form**

\begin{equation*}
f(t) = A \sin(\omega t + \varphi) + d
\end{equation*}

captures all of these features through four parameters.

**Amplitude $A$:** the maximum deviation from the center value. The function
oscillates between $d - |A|$ and $d + |A|$. For a household alternating
voltage in Europe, $A \approx 325~\text{V}$.

**Angular frequency $\omega$:** controls how fast the oscillation repeats.
The period is $T = 2\pi/\omega$. The ordinary frequency in Hz is
$f = 1/T = \omega/(2\pi)$. For European mains voltage, $f = 50~\text{Hz}$,
so $\omega = 100\pi~\text{rad/s}$.

**Phase shift $\varphi$:** shifts the entire curve horizontally. A positive
$\varphi$ shifts the curve to the left by $\varphi/\omega$. When two signals
have the same frequency but different phase shifts, we say they are
**out of phase**. Phase differences are critical in the analysis of electrical
circuits and mechanical vibrations.

**Vertical offset $d$:** shifts the entire curve up or down. For a pure AC
signal, $d = 0$. For a signal with a DC component superimposed on an
oscillation, $d \neq 0$.

```{figure} pics/fig04_general_sinusoid.svg
---
width: 75%
name: fig04_general_sinusoid
---
The general sinusoidal form $f(t) = A\sin(\omega t + \varphi) + d$ with its
four parameters labeled.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Summary and outlook

The trigonometric functions extend the triangle definitions of sine, cosine,
and tangent to all real angles via the unit circle. Sine and cosine share the
domain $\mathbb{R}$, range $[-1, 1]$, and period $2\pi$, but differ in
symmetry: cosine is even, sine is odd. The tangent has a smaller domain due to
its vertical asymptotes and period $\pi$. The general sinusoidal form with its
four parameters is the standard model for periodic signals in engineering. In
the next section we study the relationships between the trigonometric functions,
including the Pythagorean identity and the addition theorems, which are the
main algebraic tools for working with these functions.
