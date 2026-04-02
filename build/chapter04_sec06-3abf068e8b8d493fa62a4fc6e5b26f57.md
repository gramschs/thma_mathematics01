---
authors:
  - name: Simone Gramsch
---

# Limits and Continuity

Throughout this chapter we have used the word "approaches" freely and
informally. The discharging capacitor voltage approaches zero without ever
reaching it. The natural logarithm approaches negative infinity as its
argument approaches zero from the right. In section 4.1 we described $e^x$
as the unique exponential function whose rate of change at every point equals
its own value, a claim that involves asking what happens to a certain ratio
as a time interval shrinks toward zero. Each of these statements rests on the
same underlying idea. In this section we make that idea precise through the
concept of the **limit** of a function, and we use it to define the property
of **continuity**, which turns out to be the minimum requirement for the
derivative to exist.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You understand the concept of a **limit** and can read and write the
  notation $\lim_{x \to a} f(x) = L$.
* [ ] You know what **one-sided limits** are and understand when a two-sided
  limit exists.
* [ ] You know the two special limits $\lim_{x \to 0} \frac{\sin(x)}{x} = 1$
  and $\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e$.
* [ ] You know what it means for a function to be **continuous** at a point
  and can identify the common types of **discontinuity**.
```

## What does a function approach?

Let us return to the discharging capacitor from section 4.1. For simplicity
we set $U_0 = 1~\text{V}$ and $\tau = 1~\text{s}$, so the voltage across the
capacitor is:

\begin{equation*}
U_C(t) = e^{-t}.
\end{equation*}

*How fast is the capacitor losing voltage at the moment $t = 1~\text{s}$?* We
cannot answer this by looking at a single instant: a rate of change requires
two different times. Instead, we measure the average rate of voltage decrease
over a short interval from $t = 1~\text{s}$ to $t = 1 + h~\text{s}$:

\begin{equation*}
r(h) = \frac{U_C(1) - U_C(1 + h)}{h} = \frac{e^{-1} - e^{-(1+h)}}{h}.
\end{equation*}

We compute this average rate for decreasing values of $h$:

| $h~[\text{s}]$ | $r(h)~[\text{V/s}]$ |
| -------------- | -------------------- |
| 1.000 | 0.2326 |
| 0.500 | 0.2895 |
| 0.100 | 0.3501 |
| 0.010 | 0.3660 |
| 0.001 | 0.3677 |

As $h$ decreases, $r(h)$ settles toward $e^{-1} \approx 0.3679~\text{V/s}$.
Every row in the table gives a slightly different answer, but all of them
converge toward the same value. We cannot simply set $h = 0$ to find this
value, because that would require dividing by zero. What we can say is that
$r(h)$ gets arbitrarily close to $e^{-1}$ as $h$ gets arbitrarily close to
zero, regardless of from which side $h$ approaches. This is the idea of a
limit.

```{admonition} What is ... a limit?
:class: note
Let $f$ be a function defined near the point $a$, but not necessarily at $a$
itself. We say that $f(x)$ has the **limit** $L$ as $x$ approaches $a$, and
write

\begin{equation*}
\lim_{x \to a} f(x) = L,
\end{equation*}

if the values $f(x)$ get arbitrarily close to $L$ whenever $x$ gets
arbitrarily close to $a$, from either side. The value of $f$ at $x = a$
itself is irrelevant: it may be defined, undefined, or different from $L$.
```

Applying this to our example: $\lim_{h \to 0} r(h) = e^{-1}$. This limit is
the **instantaneous rate of change** of $U_C$ at $t = 1~\text{s}$. Finding
it systematically is the central task of chapter 5, where it will become the
definition of the derivative.

Limits can also be taken as $x \to \infty$. We already know that
$\lim_{t \to \infty} e^{-t} = 0$: the discharging capacitor eventually
reaches zero. Similarly, $\lim_{x \to \infty} \ln(x) = \infty$ and
$\lim_{x \to 0^+} \ln(x) = -\infty$. The notation $0^+$ indicates that $x$
approaches zero from the right, which leads us to the next concept.

```{dropdown} Video "Introduction to Limits" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/YNstP0ESndU"
title="Calculus 1 - Introduction to Limits" frameborder="0" allow="accelerometer;
autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## What if the two sides give different values?

Sometimes the value that a function approaches depends on which direction we
come from. Consider the piecewise defined height function from section 3.3:

\begin{equation*}
h(x) = \begin{cases}
-0.25\, x + 6, & x \in [0, 8], \\
4,             & x \in (8, 12], \\
-\frac{1}{3}\, x + 8, & x \in (12, 24].
\end{cases}
\end{equation*}

At the boundary point $x = 8~\text{cm}$, the first segment approaches
$h(x) \to -0.25 \cdot 8 + 6 = 4~\text{cm}$ as $x$ approaches $8$ from the
left. The second segment has the constant value $4~\text{cm}$, so it also
approaches $4~\text{cm}$ as $x$ approaches $8$ from the right. We write:

\begin{equation*}
\lim_{x \to 8^-} h(x) = 4, \qquad \lim_{x \to 8^+} h(x) = 4.
\end{equation*}

The notation $8^-$ means approaching $8$ from below and $8^+$ means
approaching from above. These are called **one-sided limits**. Because both
one-sided limits agree, the two-sided limit exists:
$\lim_{x \to 8} h(x) = 4~\text{cm}$.

```{admonition} What are ... one-sided limits?
:class: note
The **left-hand limit** $\lim_{x \to a^-} f(x) = L$ means that $f(x)$
approaches $L$ as $x$ approaches $a$ from below.

The **right-hand limit** $\lim_{x \to a^+} f(x) = L$ means that $f(x)$
approaches $L$ as $x$ approaches $a$ from above.

The two-sided limit $\lim_{x \to a} f(x)$ exists if and only if both
one-sided limits exist and are equal:

\begin{equation*}
\lim_{x \to a^-} f(x) = \lim_{x \to a^+} f(x) = L.
\end{equation*}
```

If the two one-sided limits differ, the two-sided limit does not exist. A
concrete example is the function $f(x) = |x|/x$, which equals $-1$ for all
$x < 0$ and $+1$ for all $x > 0$. As $x$ approaches zero from the left the
function approaches $-1$, and from the right it approaches $+1$. The
one-sided limits disagree, so $\lim_{x \to 0} f(x)$ does not exist. In
engineering, an electrical switch exhibits exactly this behavior: the current
jumps from zero to a finite value the instant the switch closes, with no
intermediate state.

```{dropdown} Video "One sided Limits" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/6e4Wtgc43KQ"
title="One Sided Limits, Graphs, Continuity, Infinity, Absolute Value, Squeeze Thereom -
Calculus Review" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Two limits worth knowing by heart

Two special limits appear so frequently in calculus and engineering that they
are worth knowing explicitly. Neither can be evaluated by directly
substituting the limiting value, but both can be confirmed by numerical
experiment.

**The sinc limit.** We know from section 4.4 that $\sin(x) = 0$ at $x = 0$,
so the ratio $\sin(x)/x$ takes the form $0/0$ at the origin and is undefined
there. Computing the ratio for small positive values of $x$ (measured in
radians) reveals a clear pattern:

| $x~[\text{rad}]$ | $\sin(x)$ | $\sin(x)/x$ |
| ---------------- | --------- | ------------ |
| 1.000 | 0.8415 | 0.8415 |
| 0.500 | 0.4794 | 0.9589 |
| 0.100 | 0.0998 | 0.9983 |
| 0.010 | 0.0100 | 0.9999 |

The ratio converges to $1$. This result,

\begin{equation*}
\lim_{x \to 0} \frac{\sin(x)}{x} = 1,
\end{equation*}

is one of the most important limits in calculus. It will appear in chapter 5
when we derive the derivative of the sine function. It is also the reason why
radians are the natural unit for angles in all calculus formulas: the limit
equals exactly $1$ in radians, but would equal $\pi/180$ in degrees.

**Euler's number as a limit.** In section 4.1 we introduced Euler's number
$e$ and noted its special role in differentiation. That role can already be
glimpsed in the following numerical experiment. Consider the expression
$(1 + 1/x)^x$ for increasing values of $x$:

| $x$ | $(1 + 1/x)^x$ |
| --- | -------------- |
| 1 | 2.0000 |
| 10 | 2.5937 |
| 100 | 2.7048 |
| 1000 | 2.7169 |
| 10000 | 2.7181 |

The values converge to $e \approx 2.71828$, confirming:

\begin{equation*}
\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e.
\end{equation*}

This is in fact the original definition from which Euler's number is derived.
The expression $(1 + 1/x)^x$ can be interpreted as the result of compounding
a small return of $1/x$ a total of $x$ times. As the compounding steps become
infinitely fine, the accumulated value converges to $e$. The connection
between this limit and the differentiation property of $e^x$ will be made
explicit in chapter 5.

## When is a function continuous?

The marble track from chapter 3 was physically continuous: the ball rolled
along it without ever jumping from one position to another. The mathematical
counterpart of this physical intuition is **continuity**.

The piecewise height function from section 3.3 has no jumps. We verified at
both boundary points that the segments connect: $h_1(8) = h_2(8) = 4~\text{cm}$
and $h_2(12) = h_3(12) = 4~\text{cm}$. At $x = 8~\text{cm}$, the function
value $h(8) = 4~\text{cm}$ and the limit $\lim_{x \to 8} h(x) = 4~\text{cm}$
agree. This is precisely what continuity requires.

```{admonition} What is ... continuity?
:class: note
A function $f$ is **continuous at a point** $x = a$ if three conditions hold:

* $f(a)$ is defined,
* $\lim_{x \to a} f(x)$ exists,
* $\lim_{x \to a} f(x) = f(a)$.

A function is **continuous on an interval** if it is continuous at every
point of that interval.
```

All the elementary functions we have studied in chapters 3 and 4 are
continuous on their respective domains: polynomials, exponential and
logarithmic functions, and the trigonometric functions are all continuous
wherever they are defined. Discontinuities arise precisely at the points
excluded from the domain, such as $x = 0$ for $1/x$, or at the boundaries
of piecewise functions where the pieces fail to connect.

There are three common types of discontinuity, each with a different cause.

A **removable discontinuity** occurs when the limit exists at $x = a$ but
either $f(a)$ is not defined or $f(a)$ differs from the limit. The function
$\sin(x)/x$ has a removable discontinuity at $x = 0$: the limit equals $1$
but the function is undefined there. The discontinuity can be removed by
simply defining $f(0) = 1$.

A **jump discontinuity** occurs when both one-sided limits exist but are not
equal. The function $f(x) = |x|/x$ has a jump discontinuity at $x = 0$,
as we saw above. In engineering, the closing of an electrical switch produces
a jump in the current, and the piecewise stress-strain curve of a material
at the yield point is another example.

An **infinite discontinuity** occurs when the function values grow without
bound near $x = a$. The function $f(x) = 1/x$ has an infinite discontinuity
at $x = 0$: as $x \to 0^+$ the function grows to $+\infty$, and as
$x \to 0^-$ it falls to $-\infty$. The power functions with negative integer
exponents from section 3.4 all share this property.

## Summary and outlook

The limit of a function captures the value that the function approaches near
a point, independently of the function value at that point. One-sided limits
allow us to analyze functions that behave differently from the left and from
the right, as in the piecewise functions of section 3.3. Two special limits
stand out for their importance in what follows: $\lim_{x \to 0} \sin(x)/x = 1$
will appear when we differentiate the sine function, and the limit definition
of $e$ connects back to the unique differentiation property of the natural
exponential function first described in section 4.1. Continuity is the
natural companion to the limit concept: a continuous function is one for
which the limit always agrees with the function value. In chapter 5 we will
see that continuity at a point is a necessary condition for the derivative to
exist there, and the limit notation introduced here will reappear immediately,
in the very definition of the derivative.
