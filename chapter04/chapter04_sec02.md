---
authors:
  - name: Simone Gramsch
---

# Inverse Functions

At the end of the previous section we were left with a question we could not
yet answer: at what time does the capacitor reach a given voltage? We know how
to compute the voltage for any time $t$, but now we need to run that process
in reverse. This idea of undoing a function is one of the most important
constructions in mathematics, and it leads us to the concept of the inverse
function.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know what an **inverse function** is and understand the notation
  $f^{-1}$.
* [ ] You can check whether a given function is **invertible**.
* [ ] You know that any strictly monotonic function is invertible.
* [ ] You can **calculate the inverse function** by solving the function
  equation for $x$.
* [ ] You know that the graph of $f^{-1}$ is the mirror image of the graph of
  $f$ about the line $y = x$.
* [ ] You can apply the identities $f(f^{-1}(y)) = y$ and $f^{-1}(f(x)) = x$.
```

## Reversing the capacitor question

The discharging curve from the previous section tells us the voltage across the
capacitor at any given time:

\begin{equation*}
U_C(t) = U_0 \cdot e^{-t/\tau}.
\end{equation*}

Suppose we ask: *after how much time has the voltage dropped to half its
initial value?* We need to find the time $t$ for which $U_C(t) = 0.5 \cdot U_0$.
Substituting into the formula:

\begin{equation*}
U_0 \cdot e^{-t/\tau} = 0.5 \cdot U_0.
\end{equation*}

Dividing both sides by $U_0$:

\begin{equation*}
e^{-t/\tau} = 0.5.
\end{equation*}

We need to find the value of $-t/\tau$ for which the exponential equals $0.5$.
In other words, we need to undo the exponential function. This is the problem
of finding the inverse function.

The general situation is the following. We have a function $f$ that maps an
input $x$ to an output $y = f(x)$. Given $y$, we want to find $x$. If we can
do this uniquely, that is, if every output value $y$ came from exactly one
input value $x$, then we can define a new function that maps $y$ back to $x$.
This new function is the inverse of $f$.

```{dropdown} Video "Introduction to Inverse Function" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/TN4ybFiuV3k"
title="Introduction to Inverse Functions" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## When is a function invertible?

Not every function can be inverted. Consider the squaring function
$f(x) = x^2$. If we are told that $f(x) = 9$, we cannot determine $x$
uniquely: both $x = 3$ and $x = -3$ are valid answers. The squaring function
maps two different inputs to the same output, so it cannot be inverted over
its full domain $\mathbb{R}$.

A function is invertible if and only if every output value is produced by
exactly one input value. Graphically, this means that every horizontal line
intersects the graph of the function at most once. This is called the
**horizontal line test**.

```{admonition} What is ... an invertible function?
:class: note
A function $f: X \to Y$ is called **invertible** over its domain $X$ if for
every value $y$ in the image $f(X)$ there exists exactly one $x \in X$ with
$f(x) = y$.

The **inverse function** $f^{-1}: f(X) \to X$ is then defined by

\begin{equation*}
f^{-1}(y) = x \quad \text{if and only if} \quad f(x) = y.
\end{equation*}
```

The most useful criterion for invertibility follows directly from the
properties we studied in chapter 3: any strictly monotonic function is
invertible. If $f$ is strictly increasing, then larger inputs always give
larger outputs, so no two inputs can produce the same output. The same argument
applies to strictly decreasing functions.

Since the exponential function $f(x) = e^x$ is strictly monotonically
increasing, it is invertible. This guarantees that our capacitor question has a
unique answer.

## Calculating the inverse function

To find the inverse function of a given $f$, we follow a systematic procedure.
Starting from $y = f(x)$, we solve for $x$ in terms of $y$. The resulting
expression gives us $x = f^{-1}(y)$. We then conventionally swap the roles of
$x$ and $y$ so that the inverse function is also written with $x$ as the input
variable.

**Example 1:** As a first example, let us find the inverse of the linear function
$f(x) = 3x - 5$:

1. Write $y = 3x - 5$.
2. Solve for $x$: add 5 to both sides to get $y + 5 = 3x$, then divide by 3
   to get $x = \frac{y + 5}{3}$.
3. Swap $x$ and $y$: $y = \frac{x + 5}{3}$.
4. Write as the inverse function: $f^{-1}(x) = \frac{x + 5}{3}$.

We can verify this using the two fundamental identities of inverse functions.
Applying $f$ and then $f^{-1}$ should return the original input:

\begin{equation*}
f^{-1}(f(x)) = f^{-1}(3x - 5) = \frac{(3x - 5) + 5}{3} = \frac{3x}{3} = x. \checkmark
\end{equation*}

Applying $f^{-1}$ first and then $f$ should also return the original input:

\begin{equation*}
f(f^{-1}(x)) = f\!\left(\frac{x+5}{3}\right) = 3 \cdot \frac{x+5}{3} - 5 = x + 5 - 5 = x. \checkmark
\end{equation*}

These two identities,

\begin{equation*}
f(f^{-1}(y)) = y \quad \text{and} \quad f^{-1}(f(x)) = x,
\end{equation*}

are the defining property of inverse functions. They say that $f$ and $f^{-1}$
undo each other completely.

**Example 2:** As a second example, let us find the inverse of $f(x) = x^2$ on
the restricted domain $D = [0, \infty)$. On this domain $f$ is strictly
monotonically increasing and therefore invertible:

1. Write $y = x^2$ with $x \geq 0$.
2. Solve for $x$: $x = \sqrt{y}$ (we take the positive root since $x \geq 0$).
3. Swap $x$ and $y$: $y = \sqrt{x}$.
4. Write as the inverse function: $f^{-1}(x) = \sqrt{x}$, with domain
   $[0, \infty)$.

This example illustrates an important point: when a function is not invertible
over its full domain, we can often make it invertible by restricting the domain
to an interval on which it is strictly monotonic. We will use exactly this idea
when we define the inverse functions of sine and cosine in section 4.

```{dropdown} Video "How To Find The Inverse of a Function" by The Organic Chemistry tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/2zeYEx4eTdc"
title="How To Find The Inverse of a Function" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Graphical interpretation

There is a beautiful geometric relationship between the graph of a function and
the graph of its inverse. To obtain the graph of $f^{-1}$ from the graph of
$f$, we reflect the graph of $f$ about the line $y = x$. This is because
reflecting about $y = x$ swaps the coordinates of every point: a point $(a, b)$
on the graph of $f$ (meaning $f(a) = b$) becomes the point $(b, a)$ on the
graph of $f^{-1}$ (meaning $f^{-1}(b) = a$).

```{figure} pics/fig04_inverse_function_reflection.svg
---
width: 75%
name: fig04_inverse_function_reflection
---
The graph of a function $f$ (blue) and its inverse $f^{-1}$ (orange) are
mirror images of each other about the line $y = x$ (dashed).
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

This reflection also explains what happens to the domain and range. If
$f: X \to Y$ has image $f(X)$, then $f^{-1}$ maps $f(X)$ back to $X$. The
domain and range are swapped. For our linear example, $f(x) = 3x - 5$ maps
$\mathbb{R}$ to $\mathbb{R}$, and so does $f^{-1}$. For the restricted squaring
function, $f: [0, \infty) \to [0, \infty)$ and $f^{-1} = \sqrt{x}$ also maps
$[0, \infty)$ to $[0, \infty)$.

```{dropdown} Video "Graphing Inverse Functions" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/ukEtad_aml4"
title="Graphing Inverse Functions" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Inverse Functions - Domain and Range" by The Organic Chemistry Tutor
<iframe width="1020" height="574" src="https://www.youtube.com/embed/GsIo3B46yjU"
title="Inverse Functions - Domain &amp; range-  With Fractions, Square Roots, &amp; Graphs"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

## Summary and outlook

A function is invertible when every output value comes from exactly one input
value. Strictly monotonic functions always satisfy this condition. The inverse
function is found by solving the function equation for $x$, and its graph is
the reflection of the original graph about the line $y = x$. The two identities
$f(f^{-1}(y)) = y$ and $f^{-1}(f(x)) = x$ confirm that the two functions undo
each other. We are now ready to answer the capacitor question that opened this
section: the inverse of the natural exponential function $e^x$ is the function
we call the natural logarithm, which is the subject of the next section.
