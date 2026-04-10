---
authors:
  - name: Simone Gramsch
---

# 6.2 Basic Differentiation Rules

The previous section gave us the derivative of each elementary function in
isolation. In practice, the functions we encounter are rarely single terms:
the marble track height $f(x) = 0.02\,x^2 - 0.6\,x + 6$ is a sum of three
terms, each scaled by a constant. To differentiate such expressions we need
rules that translate addition and scalar multiplication of functions into
corresponding operations on their derivatives. Three rules cover all such
cases, and together with the power rule from section 6.1 they make
differentiating any polynomial a matter of seconds.

```{admonition} Learning goals
:class: attention
* [ ] You can apply the **constant rule**: the derivative of any constant
  function is zero.
* [ ] You can apply the **factor rule**:
  $\bigl(c \cdot f(x)\bigr)' = c \cdot f'(x)$ for any constant $c$.
* [ ] You can apply the **sum rule**:
  $\bigl(f(x) + g(x)\bigr)' = f'(x) + g'(x)$.
* [ ] You can differentiate any **polynomial** by combining the sum rule, the
  factor rule, and the power rule from section 6.1.
```

## What happens to a constant under differentiation?

A constant function $f(x) = c$ assigns the same value to every input. Its
graph is a horizontal line with slope zero everywhere. The derivative
measures instantaneous slope, so the answer is immediate:

\begin{equation*}
(c)' = 0.
\end{equation*}

```{admonition} What is ... the constant rule?
:class: note
For any constant $c \in \mathbb{R}$:

\begin{equation*}
(c)' = 0.
\end{equation*}
```

This is consistent with the power rule: we can write $c = c\,x^0$, and
applying the power rule gives $c \cdot 0 \cdot x^{-1} = 0$. The constant
rule is therefore not an independent result but a special case, yet it is
worth naming explicitly because it is applied so often.

On the marble track, the term $6$ in $f(x) = 0.02\,x^2 - 0.6\,x + 6$
represents the starting height of the rail at $x = 0$. Differentiating it
gives zero: the starting height is a fixed number and contributes nothing
to the slope of the track.

## Can a constant factor be moved outside the derivative?

Suppose we scale a function by a constant factor, for instance doubling the
height of the marble track at every point. *Does the slope at every point also
double?* The answer follows directly from the limit definition. For a constant
$c$ and a differentiable function $f$:

\begin{equation*}
\bigl(c \cdot f(x)\bigr)'
= \lim_{h \to 0} \frac{c \cdot f(x + h) - c \cdot f(x)}{h}
= c \cdot \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}
= c \cdot f'(x).
\end{equation*}

The constant factor moves through the limit because it does not depend on
$h$.

```{admonition} What is ... the factor rule?
:class: note
For any constant $c \in \mathbb{R}$ and any differentiable function $f$:

\begin{equation*}
\bigl(c \cdot f(x)\bigr)' = c \cdot f'(x).
\end{equation*}
```

Applied to the track: the term $0.02\,x^2$ is the constant $0.02$ multiplied
by $x^2$. The factor rule and the power rule together give

\begin{equation*}
(0.02\,x^2)' = 0.02 \cdot (x^2)' = 0.02 \cdot 2\,x = 0.04\,x.
\end{equation*}

Similarly, $(0.6\,x)' = 0.6 \cdot (x)' = 0.6 \cdot 1 = 0.6$.

## Can a sum of functions be differentiated term by term?

The track height is a sum of three terms. *Can we differentiate each term
separately and add the results?* Again the limit definition gives a clean
answer. For two differentiable functions $f$ and $g$:

\begin{equation*}
\bigl(f(x) + g(x)\bigr)'
= \lim_{h \to 0} \frac{\bigl(f(x+h) + g(x+h)\bigr) - \bigl(f(x) + g(x)\bigr)}{h}.
\end{equation*}

Separating the numerator into two differences and splitting the limit:

\begin{equation*}
= \lim_{h \to 0} \frac{f(x+h) - f(x)}{h} + \lim_{h \to 0} \frac{g(x+h) - g(x)}{h}
= f'(x) + g'(x).
\end{equation*}

```{admonition} What is ... the sum rule?
:class: note
For any two differentiable functions $f$ and $g$:

\begin{equation*}
\bigl(f(x) + g(x)\bigr)' = f'(x) + g'(x).
\end{equation*}
```

The same argument applies to a difference: $(f - g)' = f' - g'$. And by
applying the rule repeatedly, it extends to any finite sum of terms. Every
term in a sum can be differentiated independently of the others.

## Differentiating the marble track

We now apply all three rules together to the track height. Writing out
each step explicitly:

\begin{align*}
f'(x)
&= (0.02\,x^2 - 0.6\,x + 6)' \\
&= (0.02\,x^2)' - (0.6\,x)' + (6)' \quad &&\text{sum rule}\\
&= 0.02\cdot(x^2)' - 0.6\cdot(x)' + 0 \quad &&\text{factor rule and constant rule}\\
&= 0.02 \cdot 2\,x - 0.6 \cdot 1 \quad &&\text{power rule}\\
&= 0.04\,x - 0.6.
\end{align*}

This is the same result that required the full limit calculation in section
5.3. The derivation is now four lines rather than a page, and it requires
no algebraic expansion at all.

With $f'(x) = 0.04\,x - 0.6$ in hand, we can read off physically meaningful
values immediately. At the starting block $f'(0) = -0.6$: the track descends
at $0.6~\text{cm}$ per centimetre at the entry point, its steepest section.
At the lowest point $f'(15) = 0$: the rail is momentarily horizontal, consistent
with the vertex of the parabola we located in section 3.5. At the finishing
block $f'(30) = 0.6$: the track climbs at the same rate at which it descended
at the start, reflecting the symmetry of the parabola about $x = 15~\text{cm}$.

## How does this extend to any polynomial?

The three rules above combine with the power rule to make every polynomial
differentiable in a single pass. For a general polynomial of degree $n$,

\begin{equation*}
p(x) = a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0,
\end{equation*}

the sum rule allows us to differentiate term by term, the factor rule pulls
each coefficient $a_k$ outside, and the power rule handles each $x^k$. The
result is always a polynomial of degree one lower:

\begin{equation*}
p'(x) = n\,a_n x^{n-1} + (n-1)\,a_{n-1} x^{n-2} + \cdots + a_1.
\end{equation*}

The rules of this section are in this sense the completion of the power rule:
together they form a closed toolkit for differentiating any polynomial without
ever returning to the limit definition.

## Summary and outlook

The constant rule, the factor rule, and the sum rule translate the operations
of scalar multiplication and addition of functions directly into corresponding
operations on their derivatives. Applied to the marble track height, they
reduce a calculation that required a full page in section 5.3 to four lines.
The physical reading of $f'(x)$ at the start, the vertex, and the finish of
the track confirms that the rules produce the correct slopes at each position.
Polynomials are the natural habitat of these rules, but the rules themselves
hold for any differentiable functions, not only power functions. The next
section turns to a more demanding combination: multiplication and division of
functions, where the derivative of a product is no longer simply the product
of the derivatives.
