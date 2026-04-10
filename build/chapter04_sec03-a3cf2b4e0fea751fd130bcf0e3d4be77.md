---
authors:
  - name: Simone Gramsch
---

# 4.3 Logarithmic Functions

At the end of the previous section we were left with an equation we could not
yet solve: $e^{-t/\tau} = 0.5$. We know that the exponential function is
invertible, and we know how to find inverse functions in principle. Now we
carry out that process for the exponential function explicitly. The result is
the **logarithm**, one of the most frequently used functions in science and
engineering.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **logarithm** $\log_a(x)$ as the inverse
  of the exponential function with base $a$.
* [ ] You are familiar with the **natural logarithm** $\ln(x) = \log_e(x)$ and
  know its key properties: domain, range, zeros, monotonicity, and symmetry.
* [ ] You can sketch the graph of the natural logarithm.
* [ ] You know the **calculation rules** for logarithms and can apply them.
* [ ] You can solve equations of the form $a^x = b$ using the logarithm.
```

```{dropdown} Video "Logarithms Explained" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/LRbi_pMX1DM"
title="Logarithms Explained Rules &amp; Properties, Condense, Expand, Graphing &amp;
Solving Equations Introduction" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## The logarithm as the inverse of the exponential function

We return to the capacitor discharge equation and the question from the
previous section: for which time $t$ does the voltage drop to half its initial
value? We had reduced this to:

\begin{equation*}
e^{-t/\tau} = 0.5.
\end{equation*}

Following the four-step procedure from the previous section, we write
$y = e^x$ and solve for $x$. The result is a new function: the value of $x$
for which $e^x$ equals a given positive number $y$. We call this the **natural
logarithm** of $y$ and write it as $x = \ln(y)$.

With this notation, we can immediately answer the capacitor question. From
$e^{-t/\tau} = 0.5$ we take the natural logarithm of both sides:

\begin{equation*}
-\frac{t}{\tau} = \ln(0.5) \approx -0.693.
\end{equation*}

Multiplying both sides by $-\tau$:

\begin{equation*}
t = \tau \cdot \ln(2) \approx 0.693 \cdot \tau.
\end{equation*}

The voltage drops to half its initial value after approximately $0.693$ time
constants. This quantity appears so often in physics and engineering that it
has its own name: the **half-life** of the decay process.

The natural logarithm is the inverse function of $e^x$, which means the two
functions undo each other completely:

\begin{equation*}
\ln(e^x) = x \quad \text{for all } x \in \mathbb{R},
\end{equation*}

\begin{equation*}
e^{\ln(x)} = x \quad \text{for all } x > 0.
\end{equation*}

More generally, the logarithm to base $a$ is defined as the inverse of the
exponential function with base $a$.

```{admonition} What is ... the logarithm?
:class: note
Let $a > 0$, $a \neq 1$. The **logarithm to base $a$** of a positive number
$x$ is the exponent to which $a$ must be raised to obtain $x$:

\begin{equation*}
\log_a(x) = y \quad \text{if and only if} \quad a^y = x.
\end{equation*}

The **natural logarithm** is the logarithm to base $e$:

\begin{equation*}
\ln(x) = \log_e(x).
\end{equation*}
```

## Properties of the natural logarithm

Since $\ln(x)$ is the inverse of $e^x$, its graph is the reflection of the
graph of $e^x$ about the line $y = x$. From this reflection we can read off
all the key properties directly, using the fact that domain and range swap
when a function is inverted.

**Domain.** The exponential function $e^x$ has range $(0, \infty)$, so the
natural logarithm has domain $(0, \infty)$. We cannot take the logarithm of
zero or of a negative number. This is not a formal restriction imposed from
outside: it reflects a genuine absence of a real solution to $e^y = x$ when
$x \leq 0$, since $e^y$ is always strictly positive.

**Range.** The exponential function has domain $\mathbb{R}$, so the natural
logarithm has range $\mathbb{R}$. For every real number $y$, no matter how
large or how negative, there exists a positive $x$ with $\ln(x) = y$.

**Zero.** Since $e^0 = 1$, we have $\ln(1) = 0$. The graph of the natural
logarithm crosses the $x$-axis at exactly one point: $x = 1$.

**Monotonicity.** Since $e^x$ is strictly monotonically increasing, so is its
inverse $\ln(x)$: larger inputs give larger outputs.

**Boundedness.** As $x \to \infty$, $\ln(x) \to \infty$: the natural logarithm
is unbounded above. As $x \to 0^+$, $\ln(x) \to -\infty$: the natural
logarithm is unbounded below. The $y$-axis is a vertical asymptote. The
function is therefore neither bounded above nor below.

**Symmetry.** The natural logarithm is neither even nor odd.

```{figure} pics/fig04_exp_and_ln.svg
---
width: 75%
name: fig04_exp_and_ln
---
The graphs of $e^x$ (blue) and $\ln(x)$ (orange) are reflections of each other
about the line $y = x$ (dashed). The natural logarithm is only defined for
$x > 0$.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Calculation rules for logarithms

The calculation rules for logarithms correspond directly to the calculation
rules for exponentials from the previous section. Each logarithm rule can be
derived from the corresponding exponential rule by applying $\ln$ to both sides
and using the identity $\ln(e^x) = x$.

**Product rule.** The logarithm of a product equals the sum of the logarithms:

\begin{equation*}
\ln(a \cdot b) = \ln(a) + \ln(b).
\end{equation*}

This follows from the product rule for exponentials: if $a = e^m$ and $b = e^n$,
then $a \cdot b = e^{m+n}$, so $\ln(a \cdot b) = m + n = \ln(a) + \ln(b)$.

**Quotient rule.** The logarithm of a quotient equals the difference of the
logarithms:

\begin{equation*}
\ln\!\left(\frac{a}{b}\right) = \ln(a) - \ln(b).
\end{equation*}

**Power rule.** The logarithm of a power equals the exponent times the
logarithm:

\begin{equation*}
\ln(a^n) = n \cdot \ln(a).
\end{equation*}

This rule is particularly useful for solving exponential equations: it brings
the unknown exponent down from the power to a factor, where it can be isolated
by ordinary algebra.

Let us apply these rules to solve a general exponential equation. Suppose we
want to find $x$ such that $2^x = 10$. Taking the natural logarithm of both
sides and applying the power rule:

\begin{equation*}
x \cdot \ln(2) = \ln(10),
\end{equation*}

\begin{equation*}
x = \frac{\ln(10)}{\ln(2)} \approx \frac{2.303}{0.693} \approx 3.32.
\end{equation*}

We can verify: $2^{3.32} \approx 10$. The same technique applies to any
equation of the form $a^x = b$ with $a, b > 0$ and $a \neq 1$.

## Other logarithms

The natural logarithm is the standard choice in mathematics and engineering,
but two other logarithms appear often enough to deserve mention.

The **common logarithm** $\log_{10}(x)$ uses base 10. It appears in the
definition of the decibel scale for sound and signal levels, in the pH scale
for acidity, and in the Richter scale for earthquake magnitudes. The common
logarithm is sometimes written simply as $\log(x)$ without a base, especially
in engineering contexts.

The **binary logarithm** $\log_2(x)$ uses base 2. It appears in information
theory, where the amount of information in a message is measured in bits, and
in computer science, where algorithms are analyzed by how many times a problem
can be halved before it is solved.

Any logarithm can be converted to the natural logarithm using the **change of
base formula**. For any base $a > 0$, $a \neq 1$:

\begin{equation*}
\log_a(x) = \frac{\ln(x)}{\ln(a)}.
\end{equation*}

This formula follows directly from the definition: if $\log_a(x) = y$, then
$a^y = x$, so $y \ln(a) = \ln(x)$, giving $y = \ln(x)/\ln(a)$. In practice
this means we only need one logarithm on a calculator: the natural logarithm
is sufficient to evaluate any other logarithm.

## Summary and outlook

The natural logarithm is the inverse of the natural exponential function. Its
domain is $(0, \infty)$, it has a single zero at $x = 1$, and it grows without
bound but increasingly slowly. The calculation rules for logarithms mirror those
for exponentials and are the main tool for solving equations where the unknown
appears in an exponent. Together, $e^x$ and $\ln(x)$ form a pair of inverse
functions that underpin an enormous range of engineering calculations. We now
turn to a completely different family of functions: the trigonometric functions,
which describe the oscillations and periodic phenomena that are equally
fundamental in mechanical engineering.
