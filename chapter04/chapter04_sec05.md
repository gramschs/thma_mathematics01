---
authors:
  - name: Simone Gramsch
---

# Trigonometric Identities

We now have the graphs and properties of sine, cosine, and tangent firmly in
hand. The next step is to understand the algebraic relationships between them.
These relationships, known as trigonometric identities, are the tools we will
reach for whenever we need to simplify a trigonometric expression, rewrite an
integral into a manageable form, or combine two sinusoidal signals into one.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know the relationship between sine and cosine:
  $\cos(\alpha) = \sin\!\left(\alpha + \frac{\pi}{2}\right)$ and
  $\sin(\alpha) = \cos\!\left(\alpha - \frac{\pi}{2}\right)$.
* [ ] You know the **Pythagorean identity** $\sin^2(\alpha) + \cos^2(\alpha) = 1$
  and can apply it to simplify expressions.
* [ ] You know the **addition theorems** for sine and cosine and can apply them:
  \begin{equation*}
  \sin(\alpha \pm \beta) = \sin(\alpha)\cos(\beta) \pm \cos(\alpha)\sin(\beta),
  \end{equation*}
  \begin{equation*}
  \cos(\alpha \pm \beta) = \cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta).
  \end{equation*}
* [ ] You can derive the **double angle formulas** from the addition theorems.
```

## The relationship between sine and cosine

Looking at the graphs of sine and cosine from the previous section, we notice
something striking: the two curves have exactly the same shape. The cosine
graph looks like the sine graph shifted to the left by $\pi/2$. We can verify
this by reading off the unit circle.

For any angle $\alpha$, the point on the unit circle is
$(\cos(\alpha), \sin(\alpha))$. Now consider the angle $\alpha + \pi/2$: we
have rotated a further quarter turn counterclockwise. The $x$-coordinate of
the new point is $\cos(\alpha + \pi/2)$. But rotating a point
$(\cos(\alpha), \sin(\alpha))$ by $\pi/2$ counterclockwise gives the point
$(-\sin(\alpha), \cos(\alpha))$. Reading off the $x$-coordinate:

\begin{equation*}
\cos\!\left(\alpha + \frac{\pi}{2}\right) = -\sin(\alpha).
\end{equation*}

Reading off the $y$-coordinate of the same rotated point:

\begin{equation*}
\sin\!\left(\alpha + \frac{\pi}{2}\right) = \cos(\alpha).
\end{equation*}

Rewriting the second identity with $\alpha$ replaced by $\alpha - \pi/2$:

\begin{equation*}
\sin(\alpha) = \cos\!\left(\alpha - \frac{\pi}{2}\right).
\end{equation*}

These two relationships,

\begin{equation*}
\cos(\alpha) = \sin\!\left(\alpha + \frac{\pi}{2}\right), \qquad
\sin(\alpha) = \cos\!\left(\alpha - \frac{\pi}{2}\right),
\end{equation*}

tell us that sine and cosine are the same function, just shifted by a quarter
period relative to each other. In signal analysis this shift is called a phase
difference of $\pi/2$, or equivalently $90°$. Two sinusoidal signals that
differ only by this shift are said to be in **quadrature**.

## The Pythagorean identity

Every point on the unit circle lies at distance 1 from the origin. A point on
the unit circle has coordinates $(\cos(\alpha), \sin(\alpha))$. Applying the
distance formula gives:

\begin{equation*}
\cos^2(\alpha) + \sin^2(\alpha) = 1.
\end{equation*}

This is the **Pythagorean identity**. It holds for every angle $\alpha$ without
exception and is probably the most frequently used trigonometric identity in
practice.

```{admonition} What is ... the Pythagorean identity?
:class: note
For every angle $\alpha \in \mathbb{R}$:

\begin{equation*}
\sin^2(\alpha) + \cos^2(\alpha) = 1.
\end{equation*}
```

Two immediate consequences are worth noting. First, we can express sine in
terms of cosine and vice versa:

\begin{equation*}
\sin(\alpha) = \pm\sqrt{1 - \cos^2(\alpha)}, \qquad
\cos(\alpha) = \pm\sqrt{1 - \sin^2(\alpha)},
\end{equation*}

where the sign depends on the quadrant of $\alpha$. Second, dividing the
Pythagorean identity through by $\cos^2(\alpha)$ (for $\cos(\alpha) \neq 0$)
gives an identity for the tangent:

\begin{equation*}
\frac{\sin^2(\alpha)}{\cos^2(\alpha)} + 1 = \frac{1}{\cos^2(\alpha)},
\end{equation*}

\begin{equation*}
\tan^2(\alpha) + 1 = \frac{1}{\cos^2(\alpha)}.
\end{equation*}

This identity appears in the computation of certain integrals and in the
analysis of vibrating systems.

```{dropdown} Video ""Pythagorean Identities" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/TpADRvW8zm8"
title="Pythagorean Identities - Examples &amp; Practice Problems, Trigonometry" 
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Addition theorems

The addition theorems give the sine and cosine of a sum or difference of two
angles in terms of the sines and cosines of the individual angles:

\begin{equation*}
\sin(\alpha + \beta) = \sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta),
\end{equation*}

\begin{equation*}
\sin(\alpha - \beta) = \sin(\alpha)\cos(\beta) - \cos(\alpha)\sin(\beta),
\end{equation*}

\begin{equation*}
\cos(\alpha + \beta) = \cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta),
\end{equation*}

\begin{equation*}
\cos(\alpha - \beta) = \cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta).
\end{equation*}

These four formulas can be written more compactly using the $\pm$ and $\mp$
notation, as in the learning goals, but we write them out in full here for
clarity.

**A worked example.** We use the addition theorem to compute an exact value of
$\sin(75°) = \sin(5\pi/12)$. Writing $75° = 45° + 30°$:

\begin{equation*}
\sin(75°) = \sin(45° + 30°)
= \sin(45°)\cos(30°) + \cos(45°)\sin(30°).
\end{equation*}

Substituting the standard values from the previous section:

\begin{equation*}
= \frac{\sqrt{2}}{2} \cdot \frac{\sqrt{3}}{2} + \frac{\sqrt{2}}{2} \cdot \frac{1}{2}
= \frac{\sqrt{6}}{4} + \frac{\sqrt{2}}{4} = \frac{\sqrt{6} + \sqrt{2}}{4}.
\end{equation*}

**Engineering application.** Suppose two sinusoidal signals of the same
frequency but different phase shifts are added together:

\begin{equation*}
f(t) = A_1 \sin(\omega t + \varphi_1) + A_2 \sin(\omega t + \varphi_2).
\end{equation*}

Expanding each term using the addition theorem for sine turns this into a sum
of terms involving $\sin(\omega t)$ and $\cos(\omega t)$, which can then be
combined into a single sinusoid. This technique, expanding and recombining
trigonometric expressions, is fundamental in the analysis of vibrations and
electrical circuits.

```{dropdown} Video "Sum and Difference Identities" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/sU2pyMR8GZ4"
title="Sum and Difference Identities &amp; Formulas - Sine, Cosine, Tangent - Degrees &amp;
Radians, Trigonometry" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Double angle formulas

Setting $\beta = \alpha$ in the addition theorems gives the **double angle
formulas**. For sine:

\begin{equation*}
\sin(2\alpha) = \sin(\alpha + \alpha)
= \sin(\alpha)\cos(\alpha) + \cos(\alpha)\sin(\alpha)
= 2\sin(\alpha)\cos(\alpha).
\end{equation*}

For cosine there are three equivalent forms, all obtained from
$\cos(2\alpha) = \cos^2(\alpha) - \sin^2(\alpha)$ by applying the Pythagorean
identity:

\begin{equation*}
\cos(2\alpha) = \cos^2(\alpha) - \sin^2(\alpha)
= 2\cos^2(\alpha) - 1
= 1 - 2\sin^2(\alpha).
\end{equation*}

The three forms of the cosine double angle formula are useful in different
contexts. Rearranging the second and third forms gives the **power reduction
formulas**:

\begin{equation*}
\cos^2(\alpha) = \frac{1 + \cos(2\alpha)}{2}, \qquad
\sin^2(\alpha) = \frac{1 - \cos(2\alpha)}{2}.
\end{equation*}

These formulas replace a squared trigonometric function with an unsquared one
at double the angle. They appear constantly in integral calculus: computing
the integral of $\sin^2(\alpha)$ or $\cos^2(\alpha)$ directly is awkward, but
after applying the power reduction formula the integral becomes straightforward.
We will use them in exactly this way when we reach integration.

```{dropdown}
<iframe width="1020" height="574" src="https://www.youtube.com/embed/SE5SBTgrwH8"
title="Double Angle Identities &amp; Formulas of Sin, Cos &amp; Tan - Trigonometry"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

```{dropdown} Video "Trig identities" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/m1OitPmkydY"
title="Trig Identities" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Summary and outlook

The three groups of identities in this section form the core algebraic toolkit
for trigonometric calculations. The sine-cosine phase relationship shows that
the two functions are the same oscillation viewed from a different starting
point. The Pythagorean identity connects the two functions through the geometry
of the unit circle and generates further useful identities by simple algebra.
The addition theorems allow any sum or difference of angles to be expanded, and
the double angle formulas follow as special cases. With these identities, and
the power reduction formulas in particular, we are fully prepared for the
integration techniques we will encounter in a later chapter. In the next section we introduce the concept of limits, which forms the
bridge from functions to differential calculus. For those interested, section
4.7 gives an optional introduction to the hyperbolic functions, which share a
striking structural similarity with the trigonometric functions but are built
from the exponential function.
