---
authors:
  - name: Simone Gramsch
---

# 6.4 The Chain Rule

In section 6.3 we computed the velocity of the damped oscillator and obtained
a correct and physically meaningful result. But we relied on two derivative
formulas that we used without proof: $(e^{-\delta t})' = -\delta\,e^{-\delta t}$
and $(\cos(\omega_d t))' = -\omega_d\sin(\omega_d t)$. Neither of these follows
from anything in sections 6.1 or 6.2, because both expressions are composite
functions: an elementary function applied not to the variable $t$ directly but
to a linear function of $t$. Differentiating composite functions is the task
of the chain rule, and it is the most frequently applied differentiation rule
in engineering practice.

```{admonition} Learning goals
:class: attention
* [ ] You know the **chain rule**: if $h(x) = f(g(x))$, then
  \begin{equation*}
  h'(x) = f'(g(x)) \cdot g'(x).
  \end{equation*}
* [ ] You can identify the **inner function** $g$ and the **outer function**
  $f$ in a composite expression, as practiced in section 3.6.
* [ ] You can apply the chain rule to differentiate composite functions
  involving exponential, logarithmic, trigonometric, and power functions.
```

## How does a composition change when its input changes?

In section 3.6 we defined the composition $h(x) = f(g(x))$ and practiced
identifying the inner function $g$ and the outer function $f$. The key
question was: *what is the last operation performed?* That last operation is
the outer function, and everything inside it is the inner function.

We now ask a calculus question about the same construction: if the input $x$
changes by a small amount $\Delta x$, by how much does the output $h(x)$
change? The inner function $g$ responds first, changing by approximately
$g'(x)\,\Delta x$. The outer function $f$ then responds to this intermediate
change, scaling it by $f'(g(x))$. The overall change in $h$ is approximately
the product of the two responses:

\begin{equation*}
\Delta h \approx f'(g(x)) \cdot g'(x) \cdot \Delta x.
\end{equation*}

Dividing by $\Delta x$ and passing to the limit gives the chain rule.

```{admonition} What is ... the chain rule?
:class: note
Let $g$ be differentiable at $x$ and $f$ be differentiable at $g(x)$. Then
the composition $h(x) = f(g(x))$ is differentiable at $x$ and

\begin{equation*}
h'(x) = f'\bigl(g(x)\bigr) \cdot g'(x).
\end{equation*}

In words: the derivative of the outer function evaluated at the inner
function, multiplied by the derivative of the inner function.
```

The Leibniz notation makes the chain rule particularly transparent. Writing
$u = g(x)$ and $y = f(u) = h(x)$, the chain rule reads

\begin{equation*}
\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}.
\end{equation*}

The intermediate variable $u$ appears to cancel between numerator and
denominator, just as it would in ordinary fractions. This is a mnemonic,
not a proof, but it is a reliable one and matches how engineers typically
reason about rates of change through a chain of dependencies.

## How do we differentiate the oscillator's exponential factor?

We return to the decaying exponential $f(t) = A\,e^{-\delta t}$ from section
6.3. The outer function is $e^u$ and the inner function is $u = -\delta t$.
From the reference table in section 6.1 we know $(e^u)' = e^u$, and the inner
function has derivative $(-\delta t)' = -\delta$. Applying the chain rule:

\begin{equation*}
\bigl(A\,e^{-\delta t}\bigr)'
= A \cdot e^{-\delta t} \cdot (-\delta)
= -A\delta\,e^{-\delta t}.
\end{equation*}

This confirms the result we used without proof in section 6.3. The physical
interpretation is immediate: the rate at which the envelope decays is
proportional to its current value, with $\delta$ as the constant of
proportionality. A larger damping exponent $\delta$ means a faster collapse
of the amplitude, and the derivative reflects this linearly.

As a consistency check, we evaluate at $t = 0$ with $A = 0.10~\text{m}$ and
$\delta = 0.5~\text{s}^{-1}$:

\begin{equation*}
\bigl(A\,e^{-\delta t}\bigr)'\big|_{t=0}
= -0.10 \cdot 0.5 \cdot e^{0} = -0.05~\frac{\text{m}}{\text{s}}.
\end{equation*}

At the moment of release the envelope is shrinking at $0.05~\text{m/s}$,
which matches the initial velocity we computed in section 6.3.

## How do we differentiate the oscillator's cosine factor?

The cosine factor $g(t) = \cos(\omega_d\,t)$ is the outer function $\cos(u)$
applied to the inner function $u = \omega_d\,t$. From section 6.1,
$(\cos u)' = -\sin u$, and the inner function has derivative $\omega_d$.
The chain rule gives:

\begin{equation*}
\bigl(\cos(\omega_d\,t)\bigr)'
= -\sin(\omega_d\,t) \cdot \omega_d
= -\omega_d\sin(\omega_d\,t).
\end{equation*}

This also confirms the result used in section 6.3. The factor $\omega_d$ in
front of the sine is physically the angular frequency: a higher frequency
means faster oscillation, and the derivative is correspondingly larger in
magnitude.

We can verify at $t = 0$ with $\omega_d = 3~\text{rad/s}$:

\begin{equation*}
\bigl(\cos(\omega_d\,t)\bigr)'\big|_{t=0}
= -3\sin(0) = 0.
\end{equation*}

At $t = 0$ the cosine is at its maximum value of $1$ and has zero slope,
consistent with the flat peak of the cosine graph at the origin.

## How do we handle more complex compositions?

The chain rule applies whenever one function is nested inside another,
regardless of how many layers there are. The process is always the same:
identify the outermost operation, differentiate it while treating the inner
expression as a single unit, then multiply by the derivative of that inner
expression.

Consider $h(x) = \sin(x^2)$. The outer function is $\sin(u)$ and the inner
function is $u = x^2$. Applying the chain rule:

\begin{equation*}
h'(x) = \cos(x^2) \cdot 2x.
\end{equation*}

Consider $h(x) = e^{\sin x}$. The outer function is $e^u$ and the inner
function is $u = \sin x$. Applying the chain rule:

\begin{equation*}
h'(x) = e^{\sin x} \cdot \cos x.
\end{equation*}

Consider $h(x) = \sqrt{1 - x^2}$, which we recognised as a composition in
section 3.6. Writing it as $(1 - x^2)^{1/2}$, the outer function is $u^{1/2}$
and the inner function is $u = 1 - x^2$. The chain rule and the power rule give:

\begin{equation*}
h'(x) = \frac{1}{2}(1 - x^2)^{-1/2} \cdot (-2x)
       = \frac{-x}{\sqrt{1 - x^2}}.
\end{equation*}

This last example also completes the loose end from section 6.1, where we
noted that the power rule extends to real exponents but deferred the argument.
For any $f(x) = x^r$ with real $r$, writing $x^r = e^{r\ln x}$ and applying
the chain rule gives $(x^r)' = e^{r\ln x} \cdot r/x = r\,x^{r-1}$, confirming
the power rule for all real exponents.

## Summary and outlook

The chain rule closes the justification gap left open in section 6.3: the two
derivative formulas used there for the exponential and cosine factors of the
damped oscillator both follow in a single application of the rule. The Leibniz
form $dy/dx = (dy/du)(du/dx)$ provides an intuitive reading in terms of rates
propagating through a chain of functions. The chain rule also extends the power
rule to all real exponents, completing the statement made in section 6.1. With
the product rule, the quotient rule, and the chain rule all in place, virtually
every function built from the elementary families of chapters 3 and 4 is now
differentiable in a finite number of steps. One family of functions requires
a slightly different approach: the inverse functions introduced in section 4.2,
whose derivatives follow from the chain rule by a short and elegant argument.
That argument is the subject of the next section.
