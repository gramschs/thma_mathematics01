---
authors:
  - name: Simone Gramsch
---

# 7.1 Higher-Order Derivatives

The differentiation rules assembled in chapter 6 give us a systematic way to
compute the derivative $f'$ of any combination of elementary functions. That
derivative is itself a function, defined on the same domain, and there is
nothing preventing us from applying the same rules to it again. Repeating the
process produces the higher-order derivatives, each one encoding a new layer
of information about the original function: not just how fast $f$ is changing,
but how that rate of change is itself evolving, and then how that evolution is
evolving in turn.

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **second derivative** $f''(x) = \bigl(f'(x)\bigr)'$ and of the **$n$-th derivative** $f^{(n)}(x)$.
* [ ] You are familiar with the notations $f''(x)$, $\dfrac{d^2f}{dx^2}$, and $f^{(n)}(x)$.
* [ ] You can compute higher-order derivatives of polynomials, exponential functions, and trigonometric functions.
```

## What happens when we differentiate the derivative?

In chapter 5 we derived the derivative function $f'(x) = 0.04x - 0.6$ for
the parabolic marble track $f(x) = 0.02x^2 - 0.6x + 6$. We now ask what
happens if we differentiate this derivative as well, using the power rule
from chapter 6 one more time:

\begin{equation*}
\bigl(f'(x)\bigr)' = (0.04x - 0.6)' = 0.04.
\end{equation*}

The result is a positive constant. This constant positive value means that the
slope of the marble track increases at the same rate everywhere along the track:
for each additional centimeter of horizontal distance the slope rises by exactly
$0.04$. The track curves upward at a constant rate along its entire length,
which is exactly what we expect from a parabola.

This new function is called the **second derivative** of $f$ and is written
$f''(x)$. It is the derivative of the derivative, obtained by applying the
differentiation process twice.

```{figure} pics/chap07_marble_track.svg
:name: chap07_marble_track
Graph of the marble track height profile together with its first and second
derivatives, showing the curve, the tangent slope, and the constant slope change
at a common position $x = 10$. (Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

We do not have to stop there. The second derivative is itself a function, so we
can differentiate it again. Differentiating a third time gives the **third
derivative** $f'''(x)$, a fourth time gives $f^{(4)}(x)$, and so on. For the
marble track the third derivative is $f'''(x) = (0.04)' = 0$, because the second
derivative is constant and the derivative of a constant is zero. For this
quadratic function, every derivative of order three or higher is therefore equal
to zero.

## What is the $n$-th derivative?

Applying the differentiation rules repeatedly produces a sequence of
functions. Writing $f^{(0)} = f$ for the original function and $f^{(1)} = f'$
for the first derivative, each subsequent member of the sequence is defined by
one further differentiation:

\begin{equation*}
f^{(n)}(x) = \Bigl(f^{(n-1)}(x)\Bigr)'.
\end{equation*}

```{admonition} What is ... the $n$-th derivative?
:class: note
Let $f$ be a function that can be differentiated $n$ times. The **$n$-th
derivative** of $f$ is the function $f^{(n)}$ obtained by applying the
differentiation operator $n$ times in succession:

\begin{equation*}
f^{(n)}(x) = \underbrace{\Bigl(\cdots\bigl(f'(x)\bigr)'\cdots\Bigr)'}_{\text{$n$ times}}.
\end{equation*}

We write $f' = f^{(1)}$, $f'' = f^{(2)}$, $f''' = f^{(3)}$, and use the
superscript notation $f^{(n)}$ for $n \geq 4$.
```

The Leibniz notation for higher derivatives extends the first-derivative
symbol $\dfrac{df}{dx}$ in a natural direction:

\begin{equation*}
f''(x) = \frac{d^2 f}{dx^2}, \qquad
f'''(x) = \frac{d^3 f}{dx^3}, \qquad
f^{(n)}(x) = \frac{d^n f}{dx^n}.
\end{equation*}

The superscript on $d$ counts how many times we differentiate, and the
matching superscript on $dx$ keeps the dimensional bookkeeping consistent.
Both families of notation are standard in engineering literature.

## How do we compute the higher derivatives for a roller coaster lift hill?

We now introduce the running example for this chapter, a section of a roller
coaster lift hill. The track carries passengers from the boarding platform at
ground level up to the summit of the first drop. We place the origin at the
base of the lift and measure height $h$ and horizontal distance $x$ both in
meters. The shape of the track is modeled by the cubic polynomial

\begin{equation*}
h(x) = \frac{1}{30}\,x^2 - \frac{1}{2700}\,x^3, \quad x \in [0, 60].
\end{equation*}

```{figure} pics/chap07_roller_coaster.svg
:name: chap07_roller_coaster
Graph of the roller coaster lift hill height profile $h(x) = \dfrac{1}{30}x^2 -
\dfrac{1}{2700}x^3$ on the interval $[0, 60]$, showing the base at $(0, 0)$ and
the summit at $(60, 40)$. (Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Two boundary conditions are built into this formula. At the boarding
platform we have $h(0) = 0$, so the track starts at ground level. At the
summit,

\begin{equation*}
h(60) = \frac{3600}{30} - \frac{216000}{2700} = 120 - 80 = 40~\text{m}.
\end{equation*}

The lift hill raises passengers $40~\text{m}$ over a horizontal span of
$60~\text{m}$, from the base at $x = 0$ to the summit at $x = 60$.

We now apply the power rule and constant multiple rule from chapter 6 to
compute the successive derivatives. The first derivative gives the gradient,
that is, the slope of the track at each horizontal position:

\begin{equation*}
h'(x) = \frac{x}{15} - \frac{x^2}{900} = \frac{x(60 - x)}{900}.
\end{equation*}

The factor $(60 - x)$ confirms that $h'(0) = 0$ and $h'(60) = 0$, so the track
starts horizontally at the boarding platform and levels off again at the
summit. In between, the slope is positive everywhere. Its maximum value is

\begin{equation*}
h'(30) = \frac{30 \cdot 30}{900} = 1,
\end{equation*}

reached at the midpoint $x = 30~\text{m}$, where the track inclines at
$45^\circ$.

The second derivative measures how quickly the gradient is changing:

\begin{equation*}
h''(x) = \frac{1}{15} - \frac{x}{450} = \frac{30 - x}{450}.
\end{equation*}

At $x = 0$ we have $h''(0) = \dfrac{30}{450} = \dfrac{1}{15} > 0$, so the
slope is increasing at the start of the lift. At $x = 30$ we obtain
$h''(30) = 0$, so the slope has stopped growing. At $x = 60$ we find
$h''(60) = -\dfrac{1}{15} < 0$, so the slope is now decreasing back toward
zero. The sign change of $h''$ marks a qualitative shift in the geometry of
the track, which we will examine carefully in sections 7.3 and 7.4.

The third derivative is constant:

\begin{equation*}
h'''(x) = -\frac{1}{450}.
\end{equation*}

One further differentiation gives $h^{(4)}(x) = 0$, and all higher derivatives
are zero. This is exactly what we expect. The height profile $h$ is a
polynomial of degree three, and differentiating three times reduces it to a
nonzero constant. Every derivative of order four or higher is therefore
identically zero.

## How do higher-order derivatives behave for other function families?

For polynomials the pattern is systematic. Each differentiation reduces the
degree by one, and after $n$ differentiations of a degree-$n$ polynomial we
reach a nonzero constant. One step further gives zero.

The **exponential function** $e^x$ behaves very differently. Its derivative is
itself:

\begin{equation*}
(e^x)' = e^x, \quad (e^x)'' = e^x, \quad \ldots, \quad (e^x)^{(n)} = e^x.
\end{equation*}

No matter how many times we differentiate, $e^x$ remains unchanged. This
remarkable stability is unique to the exponential and lies at the heart of why
$e^x$ solves a wide class of differential equations, which will become central
in later courses on dynamics and systems theory.

The **trigonometric functions** form a four-step cycle. Starting from $\sin x$:

\begin{equation*}
(\sin x)' = \cos x, \quad (\cos x)' = -\sin x, \quad (-\sin x)' = -\cos x,
\quad (-\cos x)' = \sin x.
\end{equation*}

After four differentiations we return to $\sin x$, so $(\sin x)^{(4)} = \sin x$.
The same four-step cycle holds for $\cos x$, shifted by one step.

## Summary and outlook

We have defined the $n$-th derivative by repeated application of the
differentiation rules of chapter 6, and we have established the standard
notations. For the roller coaster height profile
$h(x) = \frac{1}{30}x^2 - \frac{1}{2700}x^3$, the first derivative describes
the track gradient, the second derivative describes how quickly that gradient
is changing, and the third derivative is a negative constant that reflects the
cubic structure of the polynomial. The exponential function and the
trigonometric functions show that higher derivatives need not simplify or
vanish: they can remain constant or cycle indefinitely.

In the next section we turn to the direct physical meaning of these successive
derivatives when the independent variable is time. A position function, its
first derivative, and its second derivative tell the story of position,
velocity, and acceleration. The third derivative has a name of its own, and an
engineering significance that every designer of moving systems needs to know.
