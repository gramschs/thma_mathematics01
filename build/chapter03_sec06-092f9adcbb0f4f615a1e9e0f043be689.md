---
authors:
  - name: Simone Gramsch
---

# Composition of Functions

So far every function we have studied takes a number as its input and produces
a number as its output. But what if we feed the output of one function directly
into a second function as its input? This chaining of two functions into a
single operation is called the **composition of functions**, and it is one of
the most important constructions in mathematics. It is also, as we will see in
a later chapter, the foundation of the chain rule in differential calculus.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You understand the concept of **composition of functions** and know the
  notation 
  \begin{equation*}
  (f \circ g)(x) = f(g(x)).
  \end{equation*}
* [ ] You can compute $f \circ g$ and $g \circ f$ for given functions.
* [ ] You know that composition is in general **not commutative**, that is,
  $f \circ g \neq g \circ f$.
* [ ] You can identify the **inner function** and the **outer function** in a
  composite expression.
```

## Chaining two marble tracks

Imagine we connect two marble tracks in series. The ball rolls down the first
track and arrives at its finishing block at a certain height. It then continues
onto a second track, where this arrival height determines its starting position.
The second track transforms the height it receives into a new height at its own
finishing block. The entire system takes one input, the starting position on
the first track, and produces one output, the final height at the end of the
second track. Two functions have been chained into one.

Let us make this concrete. The first track transforms a position $x$ into a
height $u = g(x)$. The second track transforms a position $u$ into a height
$y = f(u)$. The combined system maps $x$ directly to $y$:

\begin{equation*}
y = f(u) = f(g(x)).
\end{equation*}

This combined mapping is the **composition** of $f$ and $g$.

```{admonition} What is ... a composition of functions?
:class: note
Let $g: X_g \to Y_g$ and $f: X_f \to Y_f$ be two functions such that the
range of $g$ is contained in the domain of $f$, that is,
$g(X_g) \subseteq Y_f$. The **composition** of $f$ and $g$ is the function

\begin{equation*}
(f \circ g): X_g \to Y_f, \quad x \mapsto f(g(x)).
\end{equation*}

We call $g$ the **inner function** and $f$ the **outer function**.
```

The notation $f \circ g$ is read as "$f$ after $g$", which reflects the order
of operations: we first apply $g$, then apply $f$ to the result.

## Computing compositions

To compute a composition $(f \circ g)(x) = f(g(x))$, we proceed in two steps:
first we evaluate the inner function $g$ at $x$, then we substitute the result
into the outer function $f$.

**Example 1:** As a first example, let $g(x) = x^2 + 1$ and $f(u) = \sqrt{u}$.
We compute $f \circ g$:

\begin{equation*}
(f \circ g)(x) = f(g(x)) = f(x^2 + 1) = \sqrt{x^2 + 1}.
\end{equation*}

We substitute the entire expression $x^2 + 1$ in place of the argument of $f$.
The domain of $f \circ g$ is all $x$ for which $g(x) = x^2 + 1 \geq 0$, which
is satisfied for all real $x$. So the domain of $f \circ g$ is $\mathbb{R}$.

**Example 2:** As a second example, let $g(x) = 3x - 1$ and $f(u) = u^2$. Then:

\begin{equation*}
(f \circ g)(x) = f(g(x)) = f(3x - 1) = (3x - 1)^2 = 9x^2 - 6x + 1.
\end{equation*}

Notice that a composition of two simple functions can produce a more complex
expression. In the first example, $f$ and $g$ were both straightforward, but
their composition $\sqrt{x^2 + 1}$ is a function we would not have written down
directly. Recognising it as a composition will be essential when we differentiate
it later.

A note on domains: the output values of the inner function $g$ must lie within
the domain of the outer function $f$. If $f = \sqrt{u}$ requires $u \geq 0$,
then we need $g(x) \geq 0$ for all $x$ in the domain of $f \circ g$. Checking
this condition is part of computing the composition correctly.

## Order matters

On our two marble tracks, connecting track A into track B is physically not the
same as connecting track B into track A. The same is true for compositions:
swapping the order of $f$ and $g$ generally produces a different function.

Using the same functions as before, $g(x) = x^2 + 1$ and $f(u) = \sqrt{u}$,
we now compute $g \circ f$ instead:

\begin{equation*}
(g \circ f)(x) = g(f(x)) = g(\sqrt{x}) = (\sqrt{x})^2 + 1 = x + 1.
\end{equation*}

The domain of $g \circ f$ is $[0, \infty)$, since $f(x) = \sqrt{x}$ requires
$x \geq 0$.

Comparing the two results:

\begin{equation*}
f \circ g: x \mapsto \sqrt{x^2 + 1}, \quad D = \mathbb{R},
\end{equation*}

\begin{equation*}
g \circ f: x \mapsto x + 1, \quad D = [0, \infty).
\end{equation*}

These are clearly different functions, with different expressions and different
domains. Composition is **not commutative**: in general, $f \circ g \neq g \circ f$.

## Identifying inner and outer functions

When we encounter a composite expression written as a single formula, we need
to be able to identify the inner and outer functions. This skill becomes
essential for the chain rule: before we can differentiate a composite function,
we must recognise it as one.

The key question is: *what is the last operation performed?* That last operation
is the outer function $f$, and everything inside it is the inner function $g$.

Consider $h(x) = (3x^2 - 5)^4$. The last operation is raising something to the
power 4, so the outer function is $f(u) = u^4$. Everything inside the brackets
is the inner function: $g(x) = 3x^2 - 5$. We can verify: $f(g(x)) = (3x^2 - 5)^4 = h(x)$.

A few more examples to practise:

| Expression $h(x)$ | Inner function $g(x)$ | Outer function $f(u)$ |
| ---- | ---- | ---- |
| $\sqrt{1 - x^2}$ | $1 - x^2$ | $\sqrt{u}$ |
| $(x^3 + 2x)^5$ | $x^3 + 2x$ | $u^5$ |
| $\frac{1}{x^2 + 1}$ | $x^2 + 1$ | $\frac{1}{u}$ |

With practice, identifying inner and outer functions becomes automatic. In each
case we ask: what is the outermost operation? Everything else is inside it.

```{dropdown} Video "Composite Functions" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/ZFPkQkURSxk"
title="Composite Functions" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Summary and outlook

The composition of functions chains two functions in sequence: the output of
the inner function becomes the input of the outer function. Composition is not
commutative, and the order of $f$ and $g$ must always be checked carefully.
Recognising a composite expression and naming its inner and outer functions is
a skill that will be needed immediately when we reach differential calculus:
the chain rule states precisely how to differentiate a composition, and it
requires exactly this decomposition. With this section we complete the
foundations of chapter 3. In the next chapter we turn to further families of
functions that are indispensable in engineering: exponential functions,
logarithms, and trigonometric functions.
