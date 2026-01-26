# Numbers

As our everyday lives become more complex, so too does the complexity of the
numbers we need to describe it. Even in kindergarten, we learn to use numbers up
to ten to determine our age or the number of guests at a birthday party, for
example. These are **natural numbers**, which are fundamental to counting.

However, when we delve into the realm of finance, our understanding of numbers
expands. For example, if we spend more money than we have available, we need
**integers** to represent a negative account balance. When we buy a cell phone
for 500 EUR, which we pay off in 24 monthly installments, we use **rational
numbers**. The monthly installment calculated as 500/24 EUR illustrates this
clearly.

Technical and scientific descriptions often require the use of **real numbers**.
A classic example is the length of the diagonal of a DIN A4 sheet, which is
calculated as $\sqrt{297^2 + 210^2}$ mm and is therefore a real number.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You know
  * **natural numbers** $\mathbb{N}$,
  * **integers** $\mathbb{Z}$,
  * **rational numbers** $\mathbb{Q}$,
  * **real numbers** $\mathbb{R}$.
* [ ] You know the embedding of numbers
  $\mathbb{N}\subset\mathbb{Z}\subset\mathbb{Q}\subset\mathbb{R}$.
```

## Natural numbers

The **natural numbers** are the numbers we learn to count with as children. We
have a brother, we are two years old, and with our parents, the family consists
of three people. The numbers have their own symbols and are written as

\begin{equation*}
1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, \dots
\end{equation*}

Sometimes the number $0$ (zero) is also counted among the natural numbers. We
denote the set of natural numbers with the symbol $\mathbb{N}$. Thus, in this
lecture we use

\begin{equation*}
\mathbb{N} = \{0, 1, 2, 3, 4, 5, \dots\}.
\end{equation*}

In school, natural numbers are often represented as a **number line**. This is
intended to help learners understand that natural numbers have an **order**, so
that, for example, the statement "3 is less than 7" is valid (in mathematical
notation: $3 < 7$). Addition and multiplication can also be explained
intuitively in this way.

```{figure} pics/fig01_line_number_N.svg
---
width: 100%
name: fig01_line_number_N
---
Number line of the natural numbers (Source: own representation; license [CC
BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

## Integers

For the equation $x + 3 = 2$, we cannot find a solution within the natural
numbers. We must extend the natural numbers in order to solve this equation. We
refer to the set of numbers

\begin{equation*}
\mathbb{Z} = \{\ldots, -3, -2, -1, 0, 1, 2, 3, 4, \ldots\}
\end{equation*}

as **integers**.

Integers are often visualized as a number line.

```{figure} pics/fig01_line_number_Z.svg
---
width: 100%
name: fig01_line_number_Z
---
Number line of integers (Source: own representation; license [CC 
BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

## Rational numbers

Even with integers, not all equations can be solved so that the result is again
an integer. For example, we cannot find an integer such that $2\cdot x = 7$.
Therefore, as an extension of integers, we introduce **rational numbers**. We
cannot write these numbers as clearly as a set, as we can with natural and
integer numbers. Instead, we define the following:

A rational number is a number that can be represented as a fraction or quotient
of two integers, whereby division by zero is not permitted. We denote the set of
rational numbers with the symbol $\mathbb{Q}$.

There are two ways of writing rational numbers:

1. as a fraction (examples $\frac{3}{8}$ or $\frac{2}{3}$) or
2. as a floating point number (examples $0.375$ or $0.\bar{6}$).

```{figure} pics/fig01_line_number_Q.svg
---
width: 100%
name: fig01_line_number_Q
---
Number line with rational numbers; there are infinitely many other rational
numbers between two rational numbers; three rational numbers are shown here as
examples in blue (source: own representation; license [CC BY-NC-SA
4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

## Real numbers

Which equation cannot be solved using rational numbers? We cannot find a
rational number as the solution for the equation $x^2 = 2$. The number $1.41421$
comes quite close to the result, since $1.41421^2 = 1.99998992$, but it is not
an exact solution, only an approximation of the exact solution. We could add
more and more decimal places

\begin{equation*} 1.414213562 \ldots, \end{equation*}

but we would never get $2$ when squaring. We denote the exact solution of the
quadratic equation $x^2 =2$ with the symbol $\sqrt{2}$ (and in fact, $-\sqrt{2}$
is another solution to this equation). Numbers that are not rational are called
**irrational**. Other examples of irrational numbers are the circle number

\begin{equation*}
\pi =3.14159\,26535\,89793\,23846\,26433\,83279\,50288\,41971\,69399\,37510\,\dots
\end{equation*}

or Euler's number

\begin{equation*}
e = 2.71828 \, 18284 \, 59045 \, 23536 \, 02874 \, 71352 \, 66249 \, 77572 \, 47093 \, 69995 \, \dots .
\end{equation*}

Irrational numbers are rarely considered on their own, which is why there is no
mathematical symbol for them. It is much more common to consider rational and
irrational numbers together. Both types of numbers are referred to as **real
numbers** and abbreviated with the mathematical symbol $\mathbb{R}$.

```{figure} pics/fig01_line_number_R.svg
---
width: 100%
name: fig01_line_number_R
---
Number line with real numbers (Source: own representation; license [CC 
BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

## Embedding the numbers

The following graphic illustrates how the numbers are continuously expanded from
natural numbers to integers, rational numbers, and ultimately real numbers.
These extensions become necessary whenever an equation cannot be solved using
this type of number. And we will see in a later chapter that real numbers are
not the end of the story, because we also want to be able to solve equations
such as $x^2 = -1$. This will lead us to **complex numbers**.

```{figure} pics/fig01_number_embedding_EN.svg
---
width: 100%
name: fig01_number_embedding_EN
---
Embedding the numbers
$\mathbb{N}\subset\mathbb{Z}\subset\mathbb{Q}\subset\mathbb{R}$ (Source: own
representation; license [CC BY-NC-SA
4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

## Summary and outlook

In this chapter, we have looked at the different types of numbers. In mechanical
engineering, we usually consider real numbers to describe technical
applications. In programming, integers and rational numbers in the form of
floating-point numbers are mainly used. We will deal with complex numbers later
on.
