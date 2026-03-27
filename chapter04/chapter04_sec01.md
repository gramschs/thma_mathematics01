---
authors:
  - name: Simone Gramsch
---

# Exponential Functions

In chapter 3 we built up a toolkit of polynomial functions by combining power
functions. Polynomials are very flexible, but they cannot describe one of the
most common behaviors in engineering: processes that grow or decay at a rate
proportional to their current value. A capacitor charging through a resistor, a
hot component cooling down, a vibration losing energy to friction: all of these
follow the same mathematical pattern, and none of them can be captured by a
polynomial. To describe them we need the exponential function.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know the definition of the **exponential function** $f(x) = a^x$ for
  a base $a > 0$, $a \neq 1$.
* [ ] You know **Euler's number** $e$ and are familiar with the **natural
  exponential function** $f(x) = e^x$.
* [ ] You know the key properties of the exponential function: domain,
  range, zeros, monotonicity, boundedness, and symmetry.
* [ ] You can sketch the graph of the exponential function for different bases.
* [ ] You know the **calculation rules** for exponential functions and can
  apply them.
```

## The capacitor charging curve

Imagine a simple electrical circuit consisting of a resistor $R$ and a
capacitor $C$ connected in series to a supply voltage $U_0$. At time $t = 0$
the circuit is switched on. The voltage across the capacitor is initially zero
and rises as charge accumulates on the capacitor plates. Our question is:
*How does the voltage across the capacitor change over time?*

```{figure} pics/fig04_rc_circuit.svg
---
width: 75%
name: fig04_rc_circuit
---
A resistor-capacitor (RC) circuit. At $t = 0$ the switch is closed and the
capacitor begins to charge.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

From the physics of the circuit, the voltage $U_C(t)$ across the capacitor as
a function of time $t$ is:

\begin{equation*}
U_C(t) = U_0 \left(1 - e^{-t/\tau}\right),
\end{equation*}

where $\tau = RC$ is the **time constant** of the circuit, measured in seconds.
At $t = 0$ we have $U_C(0) = 0$, as expected. As $t$ increases, the voltage
rises and approaches $U_0$ asymptotically: the capacitor never quite reaches
full charge, but gets arbitrarily close.

The time constant $\tau$ controls how fast this happens. After one time
constant ($t = \tau$), the voltage has reached approximately $63\%$ of the
supply voltage. After five time constants ($t = 5\tau$), it is within $1\%$ of
$U_0$, which is close enough to consider the capacitor fully charged in
practice.

The reverse process, discharging a fully charged capacitor through a resistor,
gives the curve:

\begin{equation*}
U_C(t) = U_0 \cdot e^{-t/\tau}.
\end{equation*}

Here the voltage starts at $U_0$ and decays toward zero. Both curves are built
around the same core: the expression $e^{-t/\tau}$, an exponential function of
time.

```{figure} pics/fig04_capacitor_charging.svg
---
width: 75%
name: fig04_capacitor_charging
---
Charging curve (rising) and discharging curve (falling) of a capacitor in an
RC circuit. Both are exponential functions of time.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

These curves appear throughout engineering: the temperature of a cooling
component, the amplitude of a damped oscillation, the concentration of a
substance undergoing radioactive decay, and the speed of a vehicle braking
against air resistance all follow the same exponential pattern. Understanding
the exponential function is therefore not optional for an engineer.

## Definition and properties

The general form of the exponential function is $f(x) = a^x$, where the base
$a$ is a positive real number different from 1. We require $a > 0$ because
raising a negative number to an arbitrary real exponent is not defined in
general. We require $a \neq 1$ because $1^x = 1$ for all $x$, which gives only
the constant function.

```{admonition} What is ... an exponential function?
:class: note
An **exponential function** is a function of the form

\begin{equation*}
f(x) = a^x,
\end{equation*}

where the **base** $a$ satisfies $a > 0$ and $a \neq 1$. The variable $x$ is
the exponent.
```

The key properties of the exponential function follow directly from its
definition. They are worth comparing with the polynomial properties we studied
in chapter 3.

**Domain and range.** The domain is all of $\mathbb{R}$: we can raise a
positive number to any real power. The range is $(0, \infty)$: the
exponential function is always strictly positive. In particular, $a^x = 0$ has
no solution, so the exponential function has no zeros.

**The point $(0, 1)$.** Since $a^0 = 1$ for any base $a$, every exponential
function passes through the point $(0, 1)$.

**Monotonicity.** If $a > 1$, the function is strictly monotonically
increasing: larger exponents give larger values. If $0 < a < 1$, the function
is strictly monotonically decreasing: larger exponents give smaller values. The
charging curve uses $a = e > 1$ (increasing), while the discharging curve uses
the same base but with a negative exponent, which is equivalent to using a base
less than 1 (decreasing).

**Boundedness.** For $a > 1$ the function is bounded below by 0 but unbounded
above: as $x \to +\infty$ the function grows without bound. For $0 < a < 1$
the function is also bounded below by 0 but unbounded above: as $x \to -\infty$
the function grows without bound. In both cases the value 0 is never reached,
since $a^x > 0$ for all $x$.

**Symmetry.** The exponential function is neither even nor odd. It has no
symmetry about the $y$-axis or the origin.

```{figure} pics/fig04_exponential_functions.svg
---
width: 75%
name: fig04_exponential_functions
---
Graphs of $f(x) = a^x$ for several values of $a$. All curves pass through
$(0, 1)$. Curves with $a > 1$ are increasing; curves with $0 < a < 1$ are
decreasing.
(Source: own figure; license [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Euler's number and the natural exponential function

Among all possible bases, one stands out as the natural choice for science and
engineering: **Euler's number**,

\begin{equation*}
e = 2.71828\,18284\,59045\,\ldots
\end{equation*}

This number is irrational, like $\pi$, and it appears in an enormous range of
mathematical and physical contexts. Its defining property, which we will
appreciate fully when we study differentiation, is the following: the function
$f(x) = e^x$ is the only exponential function whose rate of change at every
point equals its own value at that point. In other words, the slope of the
graph of $e^x$ at any point $x$ is exactly $e^x$. No other base has this
property.

This self-referential property makes $e^x$ the natural building block for
describing processes where the rate of change is proportional to the current
value, which is precisely the situation in our RC circuit: the charging current
is proportional to the remaining voltage difference, and the result is the
exponential charging curve.

```{admonition} What is ... the natural exponential function?
:class: note
The **natural exponential function** is $f(x) = e^x$, where
$e \approx 2.71828$ is Euler's number. It is the standard exponential function
used in science and engineering.
```

In the RC circuit, the time constant $\tau$ appears in the exponent as
$e^{-t/\tau}$. This is the natural exponential function evaluated at
$-t/\tau$, that is, a composition of the form $f(g(t))$ with inner function
$g(t) = -t/\tau$ and outer function $f(u) = e^u$. We will need this
observation when we differentiate such expressions using the chain rule.

## Calculation rules

Working with exponential expressions requires a set of algebraic rules.
These rules follow directly from the definition of exponentiation and hold for
any base $a > 0$, $a \neq 1$.

**Product rule.** When multiplying two exponentials with the same base, we add
the exponents:

\begin{equation*}
a^m \cdot a^n = a^{m+n}.
\end{equation*}

For the RC circuit: $e^{-t/\tau} \cdot e^{-s/\tau} = e^{-(t+s)/\tau}$.

**Quotient rule.** When dividing two exponentials with the same base, we
subtract the exponents:

\begin{equation*}
\frac{a^m}{a^n} = a^{m-n}.
\end{equation*}

**Power rule.** When raising an exponential to a further power, we multiply
the exponents:

\begin{equation*}
(a^m)^n = a^{m \cdot n}.
\end{equation*}

**Reciprocal.** A negative exponent gives the reciprocal:

\begin{equation*}
a^{-n} = \frac{1}{a^n}.
\end{equation*}

This is why the discharging curve $e^{-t/\tau}$ decreases toward zero: as $t$
grows, $-t/\tau$ becomes more and more negative, and $e^{-t/\tau} = 1/e^{t/\tau}$
approaches zero from above.

**Different bases.** The rules above apply when the bases are the same. To
convert between different bases, we use the identity:

\begin{equation*}
a^x = e^{x \ln a},
\end{equation*}

where $\ln$ is the natural logarithm, which we will introduce in section 4.3.

## Summary and outlook

The exponential function describes processes where a quantity grows or decays
at a rate proportional to its current value. Its key features are a domain of
all real numbers, a strictly positive range, no zeros, and monotonic
behavior controlled by the base. Among all exponential functions, $e^x$ is the
natural choice for science and engineering because of its unique property in
differentiation. The calculation rules allow us to simplify and manipulate
exponential expressions algebraically. The capacitor charging curve raises a
natural question: if we know the voltage and want to find the time at which it
was reached, we need to solve an equation of the form $e^{-t/\tau} = c$ for
$t$. This requires a function that undoes the exponential, and building that
function is the subject of the next section.
