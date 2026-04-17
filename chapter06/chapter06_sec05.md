---
authors:
  - name: Simone Gramsch
---

# 6.5 The Inverse Function Rule

In section 4.2 we constructed inverse functions by reflecting graphs about
the line $y = x$, and we noted that domain and range swap in the process. We
now ask the calculus question that naturally follows: if we know the derivative
of a function, what can we say about the derivative of its inverse? The answer
follows from the chain rule in a few lines and gives us, in one unified step,
the derivative of the natural logarithm and the derivatives of the inverse
trigonometric functions.

```{admonition} Learning goals
:class: attention
* [ ] You know the **inverse function rule**: if $f$ is differentiable and
  invertible near $x_0$, then
  \begin{equation*}
  \bigl(f^{-1}\bigr)'(y_0) = \frac{1}{f'\bigl(f^{-1}(y_0)\bigr)}.
  \end{equation*}
* [ ] You can use the inverse function rule to derive the derivatives of
  $\ln(x)$, $\arcsin(x)$, $\arccos(x)$, and $\arctan(x)$.
* [ ] You are familiar with the **inverse trigonometric functions** $\arcsin$,
  $\arccos$, and $\arctan$, their domains, and their ranges.
```

## Where does the rule come from?

In section 4.2 we established that $f$ and its inverse $f^{-1}$ undo each
other completely. Written as a composition, this means

\begin{equation*}
f\bigl(f^{-1}(y)\bigr) = y
\end{equation*}

for all $y$ in the domain of $f^{-1}$. The right-hand side is the identity
function, whose derivative is $1$. We differentiate the left-hand side using
the chain rule from section 6.4, treating $f^{-1}(y)$ as the inner function
and $f$ as the outer function:

\begin{equation*}
f'\bigl(f^{-1}(y)\bigr) \cdot \bigl(f^{-1}\bigr)'(y) = 1.
\end{equation*}

Solving for $(f^{-1})'(y)$, provided $f'(f^{-1}(y)) \neq 0$:

\begin{equation*}
\bigl(f^{-1}\bigr)'(y) = \frac{1}{f'\bigl(f^{-1}(y)\bigr)}.
\end{equation*}

```{admonition} What is ... the inverse function rule?
:class: note
Let $f$ be differentiable and invertible on an open interval, and suppose
$f'(x) \neq 0$ at every point of that interval. Then $f^{-1}$ is
differentiable and

\begin{equation*}
\bigl(f^{-1}\bigr)'(y) = \frac{1}{f'\bigl(f^{-1}(y)\bigr)}.
\end{equation*}
```

The condition $f'(x) \neq 0$ is essential: it ensures that the graph of $f$
has no horizontal tangent, which would become a vertical tangent on the
reflected graph of $f^{-1}$, and vertical tangents correspond to
non-differentiable points as we saw in section 5.4. The geometric reading of
the rule is equally direct: the slope of $f^{-1}$ at a point $y_0$ is the
reciprocal of the slope of $f$ at the corresponding point $x_0 = f^{-1}(y_0)$.
Reflection about $y = x$ swaps rise and run, which is exactly what taking a
reciprocal does to a slope.

```{dropdown} Video "Derivatives of Inverse Functions" by CodeLucky
<iframe width="1020" height="574" src="https://www.youtube.com/embed/ZBKjU6jqxWA"
title="Derivatives of Inverse Functions: The General Formula Explained (Calculus)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## What is the derivative of the natural logarithm?

We apply the rule to $f(x) = e^x$, whose inverse is $f^{-1}(y) = \ln y$.
From section 6.1 we know $f'(x) = e^x$, so $f'(f^{-1}(y)) = e^{\ln y} = y$.
The inverse function rule gives immediately:

\begin{equation*}
(\ln y)' = \frac{1}{y}, \quad y > 0.
\end{equation*}

Writing $x$ as the standard variable name:

\begin{equation*}
(\ln x)' = \frac{1}{x}, \quad x > 0.
\end{equation*}

This confirms the entry in the reference table of section 6.1 and closes the
last open item in that table. The restriction $x > 0$ reflects the domain of
the natural logarithm, which we established in section 4.3.

Returning to the damped oscillator: in section 6.3 we asked at what time the
amplitude envelope $A\,e^{-\delta t}$ drops to a prescribed fraction $\alpha$
of the initial displacement $A$. Solving $e^{-\delta t} = \alpha$ gives
$t = -\ln(\alpha)/\delta$. If we now ask how sensitive this time is to a
small change in the target fraction $\alpha$, we differentiate with respect
to $\alpha$:

\begin{equation*}
\frac{dt}{d\alpha} = -\frac{1}{\delta\,\alpha}.
\end{equation*}

For our concrete system with $\delta = 0.5~\text{s}^{-1}$ and a target of
$\alpha = 0.5$ (half the initial amplitude), this gives
$dt/d\alpha = -1/(0.5 \cdot 0.5) = -4~\text{s}$. Each additional percentage
point added to the target fraction shortens the settling time by approximately
$0.04~\text{s}$, a sensitivity figure that can inform a design decision.

## What are the inverse trigonometric functions?

In section 4.4 we noted that the sine and cosine functions are not invertible
over their full domains because they are periodic and therefore fail the
horizontal line test. The standard remedy, introduced in section 4.2, is to
restrict the domain to an interval on which the function is strictly monotonic.

The **arcsine** $\arcsin(x)$ is the inverse of $\sin$ restricted to
$[-\pi/2,\, \pi/2]$. Its domain is $[-1, 1]$ and its range is
$[-\pi/2,\, \pi/2]$.

The **arccosine** $\arccos(x)$ is the inverse of $\cos$ restricted to
$[0, \pi]$. Its domain is $[-1, 1]$ and its range is $[0, \pi]$.

The **arctangent** $\arctan(x)$ is the inverse of $\tan$ restricted to
$(-\pi/2,\, \pi/2)$. Its domain is $\mathbb{R}$ and its range is
$(-\pi/2,\, \pi/2)$.

```{admonition} What are ... the inverse trigonometric functions?
:class: note
The **inverse trigonometric functions** are defined by restricting the
trigonometric functions to intervals of strict monotonicity:

\begin{align*}
\arcsin &: [-1,\,1] \to \left[-\tfrac{\pi}{2},\, \tfrac{\pi}{2}\right], &
  \arcsin(x) &= y \iff \sin(y) = x \text{ and } y \in \left[-\tfrac{\pi}{2},\,\tfrac{\pi}{2}\right], \\[4pt]
\arccos &: [-1,\,1] \to [0,\,\pi], &
  \arccos(x) &= y \iff \cos(y) = x \text{ and } y \in [0,\,\pi], \\[4pt]
\arctan &: \mathbb{R} \to \left(-\tfrac{\pi}{2},\, \tfrac{\pi}{2}\right), &
  \arctan(x) &= y \iff \tan(y) = x \text{ and } y \in \left(-\tfrac{\pi}{2},\,\tfrac{\pi}{2}\right).
\end{align*}
```

## What are the derivatives of the inverse trigonometric functions?

We apply the inverse function rule to each of the three functions in turn.

**Derivative of $\arcsin(x)$.** Here $f(y) = \sin(y)$ on $[-\pi/2, \pi/2]$,
so $f'(y) = \cos(y)$ and $f^{-1}(x) = \arcsin(x)$. The rule gives:

\begin{equation*}
(\arcsin x)' = \frac{1}{\cos(\arcsin x)}.
\end{equation*}

We simplify the denominator using the Pythagorean identity from section 4.5.
If $y = \arcsin(x)$, then $\sin(y) = x$, so $\cos(y) = \sqrt{1 - \sin^2(y)} = \sqrt{1 - x^2}$.
We take the positive square root because $y \in [-\pi/2, \pi/2]$ and cosine
is non-negative on that interval. Therefore:

\begin{equation*}
(\arcsin x)' = \frac{1}{\sqrt{1 - x^2}}, \quad x \in (-1,\,1).
\end{equation*}

**Derivative of $\arccos(x)$.** Here $f(y) = \cos(y)$ on $[0, \pi]$, so
$f'(y) = -\sin(y)$ and $f^{-1}(x) = \arccos(x)$. The rule gives:

\begin{equation*}
(\arccos x)' = \frac{1}{-\sin(\arccos x)}.
\end{equation*}

If $y = \arccos(x)$, then $\cos(y) = x$, so
$\sin(y) = \sqrt{1 - \cos^2(y)} = \sqrt{1 - x^2}$. We take the positive
square root because $y \in [0, \pi]$ and sine is non-negative there.
Therefore:

\begin{equation*}
(\arccos x)' = \frac{-1}{\sqrt{1 - x^2}}, \quad x \in (-1,\,1).
\end{equation*}

Note that $(\arcsin x)' + (\arccos x)' = 0$, consistent with the identity
$\arcsin(x) + \arccos(x) = \pi/2$, which holds for all $x \in [-1, 1]$ and
whose derivative must indeed be zero.

**Derivative of $\arctan(x)$.** Here $f(y) = \tan(y)$ on $(-\pi/2, \pi/2)$,
so $f'(y) = 1/\cos^2(y)$ and $f^{-1}(x) = \arctan(x)$. The rule gives:

\begin{equation*}
(\arctan x)' = \cos^2(\arctan x).
\end{equation*}

If $y = \arctan(x)$, then $\tan(y) = x$. Using $\tan^2(y) + 1 = 1/\cos^2(y)$
from section 4.5, we get $\cos^2(y) = 1/(1 + \tan^2(y)) = 1/(1 + x^2)$.
Therefore:

\begin{equation*}
(\arctan x)' = \frac{1}{1 + x^2}, \quad x \in \mathbb{R}.
\end{equation*}

The arctangent derivative is defined for all real $x$, has its maximum value
of $1$ at $x = 0$, and decays to zero as $|x| \to \infty$, consistent with
the S-shaped graph of $\arctan$ flattening toward its horizontal asymptotes
$\pm\pi/2$.

## Summary and outlook

This section completes chapter 6. Starting from the chain rule applied to the
identity $f(f^{-1}(y)) = y$, we derived the inverse function rule in three
lines and used it to obtain the derivatives of $\ln x$, $\arcsin x$,
$\arccos x$, and $\arctan x$. The logarithm derivative closes the last open
entry in the reference table of section 6.1. The three inverse trigonometric
derivatives each relied on the Pythagorean identity from section 4.5,
demonstrating once more that the trigonometric identities built in chapter 4
are not background material but active tools in differentiation.

Together, chapters 5 and 6 tell a single story. Chapter 5 defined the
derivative rigorously through limits and computed it for polynomials by
direct calculation. Chapter 6 replaced that direct calculation with five
rules: the power rule, the factor and sum rules, the product and quotient
rules, the chain rule, and the inverse function rule. Every function built
from the elementary families of chapters 3 and 4 is now differentiable in a
finite number of steps, without returning to the limit definition. These rules
are the foundation on which the applications of differential calculus rest:
finding the velocity and acceleration of the damped oscillator, locating the
maxima and minima of engineering functions, and constructing the linear and
polynomial approximations that allow nonlinear problems to be handled with
linear methods.
