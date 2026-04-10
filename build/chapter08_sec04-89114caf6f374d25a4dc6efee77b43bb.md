---
authors:
  - name: Simone Gramsch
---

# 8.4 Taylor Polynomials and Taylor Series

In chapter 5 we saw that the tangent line approximates a function near a
given point using only the function value and the first derivative. A straight
line can only capture so much: it matches the curve's height and slope at
$x_0$, but it has no curvature and misses everything the second derivative
describes. By incorporating the second derivative, the third, and beyond, we
obtain polynomial approximations of progressively higher accuracy. This idea
reaches back to chapter 7's systematic treatment of higher-order derivatives
and connects everything developed in chapters 5 through 8 into a single,
powerful construction.

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **Taylor polynomial** of degree $n$ of a function $f$ at a point $x_0$:
  \begin{equation*}
  T_n(x) = \sum_{k=0}^{n} \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k.
  \end{equation*}
* [ ] You can compute the Taylor polynomial of low degree for the standard elementary functions $e^x$, $\sin(x)$, $\cos(x)$, and $\ln(1+x)$ at $x_0 = 0$.
* [ ] You understand the Taylor polynomial as a **local approximation** of $f$ near $x_0$ and can estimate the accuracy of the approximation qualitatively.
* [ ] You are familiar with the concept of the **Taylor series** as the formal limit of the Taylor polynomial as $n \to \infty$, and you know for which functions this series converges to the function itself.
```

## Why does the tangent line sometimes fall short?

A simple pendulum of length $L$ is displaced from equilibrium by an angle
$\theta$ and released. The restoring force is proportional to $\sin(\theta)$,
and the exact equation of motion is

\begin{equation*}
\ddot{\theta} = -\frac{g}{L}\,\sin(\theta).
\end{equation*}

Engineers almost universally replace $\sin(\theta)$ with $\theta$ for small
displacements. This is the **small-angle approximation**, and it is the
tangent line approximation of section 5.5 applied to the sine function at
$\theta_0 = 0$: the tangent line to $y = \sin(\theta)$ at the origin has slope
$\cos(0) = 1$, so $T_1(\theta) = \theta$. The equation of motion becomes
$\ddot{\theta} = -(g/L)\,\theta$, a linear equation with the well-known
harmonic solution.

*How accurate is this?* At $\theta = 0.5~\text{rad}$ (about $29°$):

\begin{equation*}
\sin(0.5) = 0.4794, \qquad T_1(0.5) = 0.5. \qquad \text{Error: } 4.3\,\%.
\end{equation*}

The error of roughly 4 percent is acceptable in many applications, but a
structural engineer computing the tension in a pendulum rod under dynamic
loading may require better accuracy. At $\theta = 1.0~\text{rad}$ (about
$57°$) the error in $T_1$ exceeds 18 percent. The tangent line is no longer
adequate, and we need to add further terms.

## What is the Taylor polynomial?

The tangent line at $x_0$ is the unique polynomial of degree at most 1 that
matches $f$ in value and slope at $x_0$:

\begin{equation*}
T_1(x) = f(x_0) + f'(x_0)(x - x_0).
\end{equation*}

To do better, we add a quadratic correction whose coefficient is chosen so that
the second derivative of $T_2$ at $x_0$ equals $f''(x_0)$. The unique quadratic
satisfying this requirement, together with the value and slope conditions, is

\begin{equation*}
T_2(x) = f(x_0) + f'(x_0)(x - x_0) + \frac{f''(x_0)}{2}(x - x_0)^2.
\end{equation*}

Adding a cubic term whose coefficient ensures the third derivative matches:

\begin{equation*}
T_3(x) = T_2(x) + \frac{f'''(x_0)}{6}(x - x_0)^3.
\end{equation*}

The pattern is clear. At each step we append one term whose $k$-th derivative
at $x_0$ equals $f^{(k)}(x_0)$. The coefficient of $(x - x_0)^k$ must be
$f^{(k)}(x_0) / k!$, because differentiating $(x - x_0)^k$ exactly $k$ times
yields $k!$, and dividing by $k!$ cancels this factor.

```{admonition} What is ... the Taylor polynomial?
:class: note
Let $f$ be $n$ times differentiable at $x_0$. The **Taylor polynomial of
degree $n$** of $f$ at $x_0$ is

\begin{equation*}
T_n(x) = \sum_{k=0}^{n} \frac{f^{(k)}(x_0)}{k!}\,(x - x_0)^k.
\end{equation*}

It is the unique polynomial of degree at most $n$ that matches $f$ and its
first $n$ derivatives at $x_0$:

\begin{equation*}
T_n^{(k)}(x_0) = f^{(k)}(x_0), \quad k = 0, 1, \ldots, n.
\end{equation*}
```

We now build the Taylor polynomials of $\sin(\theta)$ at $\theta_0 = 0$.
Using the cyclic differentiation pattern from section 7.1:

\begin{align*}
(\sin\theta)^{(0)}\big|_0 &= 0, &
(\sin\theta)^{(1)}\big|_0 &= 1, \\
(\sin\theta)^{(2)}\big|_0 &= 0, &
(\sin\theta)^{(3)}\big|_0 &= -1, \\
(\sin\theta)^{(4)}\big|_0 &= 0, &
(\sin\theta)^{(5)}\big|_0 &= 1.
\end{align*}

Only the odd-degree derivatives contribute (the even ones vanish at $0$):

\begin{equation*}
T_1(\theta) = \theta,
\qquad
T_3(\theta) = \theta - \frac{\theta^3}{6},
\qquad
T_5(\theta) = \theta - \frac{\theta^3}{6} + \frac{\theta^5}{120}.
\end{equation*}

At $\theta = 0.5~\text{rad}$:

| Approximation | Value | Error |
| --- | --- | --- |
| Exact $\sin(0.5)$ | $0.47943$ | |
| $T_1(0.5) = 0.5$ | $0.50000$ | $4.3\,\%$ |
| $T_3(0.5) = 0.5 - 0.02083$ | $0.47917$ | $0.05\,\%$ |
| $T_5(0.5) \approx 0.47917 + 0.00026$ | $0.47943$ | $< 0.01\,\%$ |

Each additional pair of terms reduces the error by roughly two orders of
magnitude at $\theta = 0.5$. At $\theta = 1.0~\text{rad}$ the improvement is
still dramatic: $T_3(1) = 1 - \frac{1}{6} \approx 0.833$ reduces the error
from 18.8 percent to about 1 percent, and $T_5(1) \approx 0.842$ is within
0.03 percent of the exact value.

## How do we compute Taylor polynomials for the standard functions?

The recipe is always the same: evaluate $f$ and its derivatives at $x_0 = 0$,
divide each value by the appropriate factorial, and write the sum.

**Exponential function.** Every derivative of $e^x$ equals $e^x$, and
$e^0 = 1$, so all coefficients are 1. The Taylor polynomial of degree $n$ at
$x_0 = 0$ is

\begin{equation*}
T_n(x) = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + \cdots + \frac{x^n}{n!}.
\end{equation*}

This is the most important approximation in applied mathematics. For an RC
circuit discharging with time constant $\tau$, the voltage follows
$V(t) = V_0 e^{-t/\tau}$. For short times $t \ll \tau$ the approximation
$T_1 = V_0(1 - t/\tau)$ gives the linear decay rate used in quick design
estimates, and $T_2 = V_0(1 - t/\tau + t^2/(2\tau^2))$ captures the
beginning of the curvature.

**Cosine.** Only even-order derivatives of $\cos(x)$ contribute at $x_0 = 0$
(the odd ones vanish there):

\begin{equation*}
T_2(x) = 1 - \frac{x^2}{2},
\qquad
T_4(x) = 1 - \frac{x^2}{2} + \frac{x^4}{24}.
\end{equation*}

**Natural logarithm.** For $\ln(1+x)$ at $x_0 = 0$ the successive derivatives
alternate in sign:

\begin{equation*}
T_n(x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \cdots +
(-1)^{n+1}\frac{x^n}{n}.
\end{equation*}

Unlike the exponential and trigonometric polynomials, this series converges
only for $|x| \leq 1$, and the approximation is accurate only near $x = 0$.

```{raw} html
<!--
  SVELTE APP: "Taylor polynomial explorer"

  Main panel: the graph of sin(x) in dark blue on [-2π, 2π].
  Overlaid Taylor polynomials T₁, T₃, T₅, T₇ drawn progressively in
  lighter shades, selectable via a toggle or slider for degree n.

  A vertical dashed line at a movable point x0 (default x0 = 0).
  The tangent approximation error |sin(x0) - Tn(x0)| shown in an info tile.

  A second panel shows the same comparison for cos(x) with T₂ and T₄,
  toggled by a tab.

  Preset buttons: "Small angle (0.3 rad)", "Moderate (0.7 rad)",
  "Large (1.5 rad)" let students jump to angles of engineering interest.

  Purpose: students see visually how each additional pair of terms extends
  the "good approximation" interval further from x0 = 0. The error tile
  quantifies what the graph suggests.
-->
```

## How good is the approximation?

The Taylor polynomial $T_n$ is designed to match $f$ at $x_0$ in value and
in all derivatives up to order $n$. Away from $x_0$ the approximation
degrades, and the rate of degradation depends on how large $(x - x_0)$ is
and how quickly the higher derivatives of $f$ grow.

A precise statement uses the **remainder**: $f(x) = T_n(x) + R_n(x)$, where
$R_n(x)$ is the error of the $n$-th degree approximation. It can be shown
that $|R_n(x)|$ is bounded by a term proportional to $|x - x_0|^{n+1}$, so
the error shrinks as $x$ approaches $x_0$ at least as fast as $(x - x_0)^{n+1}$.
Doubling the distance from $x_0$ multiplies the error by at most $2^{n+1}$,
so higher-degree polynomials tolerate larger distances before the error
becomes significant.

This confirms the pattern observed in the table for $\sin(\theta)$: the error
at $\theta = 0.5$ dropped by roughly $10^2$ when we went from $T_1$ to $T_3$,
because the new leading error term scaled as $0.5^5 / 120 \approx 2.6 \times 10^{-4}$.

For the small-angle approximation in the pendulum, the designer can estimate
in advance how large an angle $\theta_{\max}$ is tolerable. If the restoring
force must be accurate to within $1$ percent, then $|(\theta - \sin\theta)/\sin\theta| < 0.01$,
which (using $\sin\theta \approx \theta - \theta^3/6$) gives $\theta^2/6 < 0.01$
and hence $\theta_{\max} \approx 0.24~\text{rad} \approx 14°$. This bound is
derived directly from the third-order Taylor term.

## What is the Taylor series?

The Taylor polynomials $T_1, T_2, T_3, \ldots$ form an infinite sequence of
approximations, each one more accurate than the last near $x_0$. The formal
limit of this sequence, if it converges, is the **Taylor series**:

\begin{equation*}
\sum_{k=0}^{\infty} \frac{f^{(k)}(x_0)}{k!}\,(x - x_0)^k.
\end{equation*}

For the exponential function $e^x$, the sine, and the cosine, this series
converges to the function itself for every real $x$. These functions are
called **entire**, meaning they are perfectly captured by their Taylor series
at any centre $x_0$ and on the whole real line.

For $\ln(1+x)$ the situation is different: the series converges only for
$|x| \leq 1$ (with the boundary case $x = 1$ also converging). At $x = 2$,
for instance, the partial sums do not approach $\ln 3$. The interval on
which the series converges is called the **radius of convergence**, and
different functions have different radii.

Not every function equals its Taylor series even within the radius of
convergence. A famous counterexample is $f(x) = e^{-1/x^2}$ (extended
by $f(0) = 0$): all its derivatives at $x_0 = 0$ are zero, so the Taylor
series is identically zero, yet $f(x) > 0$ for all $x \neq 0$. Functions
for which the Taylor series converges to the function itself are called
**analytic**, and all the elementary functions of engineering mathematics
are analytic on their natural domains.

## Where do Taylor polynomials appear in engineering?

Taylor polynomials appear wherever a nonlinear function must be handled by
linear or polynomial methods.

In dynamics and control engineering, the nonlinear equation of motion of a
system is **linearised** about a steady operating point $x_0$ by replacing
$f(x)$ with $T_1(x) = f(x_0) + f'(x_0)(x - x_0)$. The resulting linear
system can be analysed with the full toolkit of linear control theory. We
used exactly this idea in section 5.5 when we discussed the tangent line as
a linear approximation, but now we can quantify the error and decide how
close to $x_0$ the linearisation remains valid.

In numerical analysis, the Taylor expansion of a function at the grid points
of a computational mesh is the foundation of finite-difference methods for
differential equations. The second-order central difference approximation
$f''(x) \approx [f(x+h) - 2f(x) + f(x-h)]/h^2$ is derived by expanding
$f(x \pm h)$ to third order in $h$ and combining: the first and third
derivative terms cancel, and the second-order term yields $f''$ with an
error of order $h^2$. Without the Taylor expansion this formula has no
systematic justification.

In the mechanics of materials, the Euler-Bernoulli beam equation relates the
bending curvature to the applied moment. The exact curvature formula involves
$[1 + (y')^2]^{3/2}$ in the denominator. For small deflections $|y'| \ll 1$
the Taylor expansion gives $[1 + (y')^2]^{3/2} \approx 1$, reducing the
equation to the standard linear beam theory. The small-deflection assumption
is quantified by the second-order term in the expansion and tested against the
actual deflection slope in the design.

## Summary and outlook

We have defined the Taylor polynomial $T_n$ as the unique degree-$n$
polynomial that matches $f$ in value and all derivatives up to order $n$
at a chosen point $x_0$. For the sine function at $x_0 = 0$, successive
polynomials $T_1$, $T_3$, $T_5$ reduce the approximation error at
$\theta = 0.5~\text{rad}$ from 4.3 percent to essentially zero by the
fifth degree. The exponential, cosine, and logarithm follow the same
pattern, each with its own coefficient sequence derived from the
higher-order derivatives of chapter 7. The Taylor series extends the
polynomial to an infinite sum and, for entire functions such as $e^x$,
$\sin(x)$, and $\cos(x)$, converges to the function everywhere.

This chapter has developed the full apparatus of differential calculus in one
variable. Starting from the derivative as the instantaneous rate of change,
we moved through differentiation rules, higher-order derivatives, and the
geometric interpretation of the second derivative, reaching in this final
section an approximation theory that unifies all of those ideas. The local
extrema of section 8.1, the curve sketching of section 8.2, the constrained
optimisation of section 8.3, and the Taylor polynomial of this section are
four facets of the same underlying insight: a differentiable function is
completely characterised, near any given point, by the sequence of values
$f(x_0),\, f'(x_0),\, f''(x_0), \ldots$ The next chapter opens the second
major branch of the calculus, integration, which asks not how a function
changes but how its values accumulate, and which will turn out to be
connected to differentiation in the deepest possible way.
