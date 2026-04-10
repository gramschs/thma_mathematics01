---
authors:
  - name: Simone Gramsch
---

# 6.3 Product Rule and Quotient Rule

The rules of section 6.2 allow us to differentiate any sum or scalar multiple
of elementary functions, and together with the power rule they make every
polynomial routine. But functions in mechanical engineering are rarely just
sums. The position of a damped oscillator, for example, is a product of an
exponential decay and a cosine oscillation: two non-trivial functions multiplied
together. No combination of the sum and factor rules can handle such an
expression. We need a rule for products, and a companion rule for quotients.

```{admonition} Learning goals
:class: attention
* [ ] You know the **product rule**
  $\bigl(f \cdot g\bigr)' = f' \cdot g + f \cdot g'$
  and can apply it to products of elementary functions.
* [ ] You know the **quotient rule**
  $\left(\dfrac{f}{g}\right)' = \dfrac{f' \cdot g - f \cdot g'}{g^2}$
  and can apply it wherever $g \neq 0$.
* [ ] You can identify when the product or quotient rule is needed and carry
  out the differentiation correctly, including simplification of the result.
```

## How does a damped oscillator move?

A mass attached to a spring and a viscous damper is one of the most
fundamental models in mechanical engineering. The spring pulls the mass back
toward equilibrium with a force proportional to the displacement; the damper
resists motion with a force proportional to the velocity and converts kinetic
energy into heat. When the mass is displaced and released, it does not
oscillate indefinitely: the amplitude shrinks with every cycle as the damper
dissipates energy.

```{figure} pics/fig06_damped_oscillator.svg
---
width: 75%
name: fig06_damped_oscillator
---
A mass-spring-damper system. The mass $m$ is displaced from its equilibrium
position and released. The resulting motion is a damped oscillation.
(Source: own figure; licence [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

We measure the displacement of the mass from its equilibrium position and call
it $x$, with positive values to the right. For a system with moderate damping,
the position as a function of time is

\begin{equation*}
x(t) = A\,e^{-\delta t}\cos(\omega_d\, t),
\end{equation*}

where $A$ is the initial displacement in metres, $\delta > 0$ is the
**damping exponent** in $\text{s}^{-1}$, and $\omega_d$ is the **damped
natural frequency** in $\text{rad/s}$. At $t = 0$ we have $x(0) = A$,
confirming that the mass starts at the prescribed displacement. As $t$
increases, the factor $e^{-\delta t}$ shrinks toward zero and the oscillation
dies away.

For a concrete system we use $A = 0.10~\text{m}$,
$\delta = 0.5~\text{s}^{-1}$, and $\omega_d = 3~\text{rad/s}$:

\begin{equation*}
x(t) = 0.10\,e^{-0.5\,t}\cos(3t).
\end{equation*}

*How fast is the mass moving, and in which direction?* The velocity $v(t) = x'(t)$
is what we want, and computing it requires differentiating a product of two
functions. Neither the marble track nor any polynomial from sections 6.1 and
6.2 prepared us for this: we need a new rule.

## What is the product rule?

We apply the limit definition directly to the product $f(x)\cdot g(x)$. The
standard approach is to add and subtract a bridge term $f(x)\,g(x+h)$ in the
numerator, which allows the difference quotient to be split into two
recognisable pieces:

\begin{align*}
\bigl(f \cdot g\bigr)'(x)
&= \lim_{h \to 0}
   \frac{f(x+h)\,g(x+h) - f(x)\,g(x)}{h} \\[4pt]
&= \lim_{h \to 0}
   \frac{f(x+h)\,g(x+h) - f(x)\,g(x+h)
         + f(x)\,g(x+h) - f(x)\,g(x)}{h} \\[4pt]
&= \lim_{h \to 0}
   \frac{f(x+h) - f(x)}{h}\cdot g(x+h)
   \;+\;
   f(x)\cdot \lim_{h \to 0}
   \frac{g(x+h) - g(x)}{h}.
\end{align*}

As $h \to 0$, the first ratio approaches $f'(x)$ and $g(x + h)$ approaches
$g(x)$ by continuity. The second ratio approaches $g'(x)$. We arrive at

\begin{equation*}
\bigl(f \cdot g\bigr)' = f' \cdot g + f \cdot g'.
\end{equation*}

```{admonition} What is ... the product rule?
:class: note
For any two differentiable functions $f$ and $g$:

\begin{equation*}
\bigl(f(x) \cdot g(x)\bigr)' = f'(x) \cdot g(x) + f(x) \cdot g'(x).
\end{equation*}
```

A useful way to read this rule aloud is: derivative of the first times the
second, plus the first times the derivative of the second. The two terms
capture the independent contribution of each factor to the overall rate of
change.

Notice that the rule is not symmetric: $(f \cdot g)' \neq f' \cdot g'$.
The product of the derivatives is not the derivative of the product, just as
the composition of two functions is not the composition of their derivatives,
as we discussed in section 3.6.

## What is the velocity of the damped oscillator?

We apply the product rule to $x(t) = A\,e^{-\delta t}\cos(\omega_d\,t)$,
identifying $f(t) = A\,e^{-\delta t}$ and $g(t) = \cos(\omega_d\,t)$.

The derivatives of these two factors each involve a composition: $e^{-\delta t}$
is $e^u$ evaluated at $u = -\delta t$, and $\cos(\omega_d\,t)$ is $\cos(u)$
evaluated at $u = \omega_d\,t$. As section 6.4 will confirm using the chain
rule, their derivatives are

\begin{equation*}
f'(t) = -A\delta\,e^{-\delta t}, \qquad g'(t) = -\omega_d\sin(\omega_d\,t).
\end{equation*}

The product rule then gives the velocity:

\begin{align*}
v(t) = x'(t)
&= f'(t)\,g(t) + f(t)\,g'(t) \\
&= -A\delta\,e^{-\delta t}\cos(\omega_d\,t) - A\omega_d\,e^{-\delta t}\sin(\omega_d\,t) \\
&= -A\,e^{-\delta t}\bigl(\delta\cos(\omega_d\,t) + \omega_d\sin(\omega_d\,t)\bigr).
\end{align*}

The velocity is itself a product of the decaying envelope $e^{-\delta t}$ and
an oscillating term, so it also decays to zero as $t \to \infty$, as expected
for a system losing energy continuously.

We verify the result at $t = 0$ with the concrete values
$A = 0.10~\text{m}$, $\delta = 0.5~\text{s}^{-1}$, $\omega_d = 3~\text{rad/s}$:

\begin{equation*}
v(0) = -0.10\,e^{0}\bigl(0.5 \cdot \cos(0) + 3 \cdot \sin(0)\bigr)
     = -0.10 \cdot 1 \cdot (0.5 \cdot 1 + 3 \cdot 0)
     = -0.05~\frac{\text{m}}{\text{s}}.
\end{equation*}

At the moment of release the mass is moving at $0.05~\text{m/s}$ back toward
equilibrium. The negative sign confirms the direction: the mass starts at
positive displacement $x(0) = 0.10~\text{m}$ and the restoring force is
already pulling it inward, so the initial velocity is indeed directed toward
the origin.

## What is the quotient rule?

Products and quotients are closely related, and the quotient rule can be
derived directly from the product rule without returning to the limit
definition. Let $q(x) = f(x)/g(x)$, so that $f(x) = q(x)\cdot g(x)$.
Differentiating both sides with the product rule:

\begin{equation*}
f'(x) = q'(x)\cdot g(x) + q(x)\cdot g'(x).
\end{equation*}

Solving for $q'(x)$ and substituting $q(x) = f(x)/g(x)$:

\begin{equation*}
q'(x) = \frac{f'(x) - q(x)\cdot g'(x)}{g(x)}
       = \frac{f'(x) - \dfrac{f(x)}{g(x)}\cdot g'(x)}{g(x)}
       = \frac{f'(x)\,g(x) - f(x)\,g'(x)}{g(x)^2}.
\end{equation*}

```{admonition} What is ... the quotient rule?
:class: note
For two differentiable functions $f$ and $g$ with $g(x) \neq 0$:

\begin{equation*}
\left(\frac{f(x)}{g(x)}\right)' = \frac{f'(x)\,g(x) - f(x)\,g'(x)}{g(x)^2}.
\end{equation*}
```

The order of terms in the numerator matters: it is always $f'g$ minus $f g'$,
never the other way around. A sign error here produces a result that is wrong
by a sign and a factor of two, so it is worth double-checking by substituting
a simple example.

## Can we verify the derivative of the tangent?

In section 6.1 we stated without proof that $(\tan x)' = 1/\cos^2 x$. The
quotient rule now lets us derive this result. We write $\tan x = \sin x / \cos x$
and identify $f(x) = \sin x$ and $g(x) = \cos x$, so $f'(x) = \cos x$ and
$g'(x) = -\sin x$. Applying the quotient rule:

\begin{equation*}
(\tan x)' = \frac{\cos x \cdot \cos x - \sin x \cdot (-\sin x)}{\cos^2 x}
          = \frac{\cos^2 x + \sin^2 x}{\cos^2 x}.
\end{equation*}

The numerator is exactly the Pythagorean identity from section 4.5:
$\cos^2 x + \sin^2 x = 1$. Therefore

\begin{equation*}
(\tan x)' = \frac{1}{\cos^2 x},
\end{equation*}

confirming the entry in the reference table of section 6.1. The Pythagorean
identity, which we proved geometrically from the unit circle, turns out to
play an algebraic role in differential calculus as well.

## Summary and outlook

The product rule and the quotient rule complete the toolkit for differentiating
algebraic combinations of functions. Applied to the damped oscillator, the
product rule produces the velocity in a direct calculation, and the result
decays to zero as expected from the physical model. The quotient rule,
derived from the product rule without a separate limit argument, closes the
open item from section 6.1 by giving a clean derivation of $(\tan x)' = 1/\cos^2 x$.
Both rules required knowing the derivatives of the individual factors, and in
the oscillator example those factors were composite functions whose derivatives
we used without yet justifying them. Providing that justification is the task
of the next section, where the chain rule handles any composition of
differentiable functions.
