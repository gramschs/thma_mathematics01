# Calculating with sets

We can calculate with sets just as we do with numbers. These 'calculation rules'
may seem abstract at first glance, but they form the basis of programming, the
construction of electrical circuits, and the design of CAD objects.

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You can construct the **intersection** of two sets and interpret the
  result of the operation as a **logical AND**.
* [ ] You can construct the **union** of two sets and interpret it as the result
  of the **logical OR** operation.
* [ ] You can construct the **difference** of two sets and know what the
  **complement** is.
```

## Intersection

Two friends want to train together at the gym. Anna has time to train on the
following days:

\begin{equation*}
A = \{\text{Monday}, \text{Thursday}, \text{Saturday}, \text{Sunday}\}.
\end{equation*}

Bob, on the other hand, can only train on the days

\begin{equation*}
B = \{\text{Monday}, \text{Wednesday}, \text{Friday}, \text{Sunday}\}.
\end{equation*}

If they both want to train together, they can meet on the days

\begin{equation*}
A \cap B = \{\text{Monday}, \text{Sunday}\}
\end{equation*}.

We call this set the **intersection**. The intersection is created by going
through the days in Anna's set and checking whether that day is also in Bob's
set of possible training days. The intersection is therefore created by a day in
the intersection being in Anna's set **AND** in Bob's set.

```{figure} pics/fig01_intersection_EN.svg
---
width: 100%
name: fig01_intersection_EN
---
Venn diagram showing the intersection $A\cap B$ (Source: own representation;
license [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

We write mathematically briefly

\begin{equation*}
A\cap B = \{ x \,|\, x\in A \land x\in B \}.
\end{equation*}

In words: The intersection of $A$ and $B$ is equal to the set of all $x$ such
that $x$ is an element of the set $A$ *and* $x$ is an element of the set $B$.
The symbol $\cap$ stands for intersection and the symbol $\land$ stands for
logical AND.

If Anna and Bob had no time together on any day, the intersection would be
empty, i.e., $A\cap B = \emptyset$ or $A\cap B=\{\}$.

## Union

A third friend joins them, Charlie also likes to work out at the gym. She
doesn't want to work out alone, but it doesn't matter to her whether she works
out with Anna or Bob. The set of possible days on which she wouldn't have to go
to the gym alone is therefore

\begin{equation*}
A\cup B=\{\text{Monday}, \text{Wednesday}, \text{Thursday}, \text{Friday},
\text{Saturday}, \text{Sunday}.\}
\end{equation*}

```{figure} pics/fig01_union_EN.svg
---
width: 100%
name: fig01_union_EN
---
Venn diagram showing the union $A\cup B$ (Source: own representation;
license [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

This so-called **union set** is therefore the result of either Anna going to the
gym **OR** Bob going to the gym (or both, as on Monday and Sunday,
respectively). The logical OR is abbreviated with the symbol $\lor$. We can
therefore mathematically denote the union set with the symbol $\cup$ as follows:

\begin{equation*}
A\cup B = \{x \,|\, x\in A \lor x\in B\}.
\end{equation*}

In words: The union set of $A$ and $B$ is equal to the set of all $x$ such that
$x$ is an element of the set $A$ *or* $x$ is an element of the set $B$.

## Difference

Unfortunately, Charlie has fallen out with Bob. She still wants to go to the gym
with Anna, but she doesn't want to run into Bob there under any circumstances.
So she now forms the so-called **difference set** $A\setminus B$ to find out on
which days she can go to the gym. She goes through Anna's days, but crosses off
the day if it appears in Bob's set. That leaves Thursday and Saturday.

```{figure} pics/fig01_difference_set_EN.svg
---
width: 100%
name: fig01_difference_set_EN
---
Venn diagram showing the difference set $A\setminus B$ (Source: own representation;
license [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

In mathematical notation, we write the difference set as follows:

\begin{equation*}
A\setminus B=\{\text{Thursday}, \text{Saturday}\}.
\end{equation*}

In general, the difference set is defined as

\begin{equation*}
A\setminus B = \{x \,|\, x\in A \land x\notin B \}
\end{equation*}.

In words, the difference set of $A$ and $B$ is the set of all $x$ such that $x$
is in the set $A$ *and* at the same time $x$ is not in the set $B$.

## Complement

After a while, Charlie realizes that she can train quite well on her own.
Whether Anna is there or not becomes less and less important to her. Only Bob is
someone she still doesn't want to meet. If she now goes through the set of *all*
weekdays, i.e.

\begin{equation*}
W = \{\text{Monday},\text{Tuesday},\text{Wednesday},\text{Thursday},\text{Friday},
\text{Saturday}, \text{Sunday}\}
\end{equation*}

and then crosses out the days when Bob goes to the gym, she forms the so-called
**complement**:

\begin{equation*}
W\setminus B = \{\text{Tuesday}, \text{Thursday}, \text{Saturday}\}.
\end{equation*}

```{figure} pics/fig01_complement_EN.svg
---
width: 100%
name: fig01_complement_EN
---
Venn diagram showing the complement $B^{C}=\bar{B}$ with respect to $W$ (Source:
own representation; license [CC BY-NC-SA
4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

What is the difference between this and a difference set? A difference set can
be formed between any two sets. With a complement, on the other hand, we define
a base set (in this case, all seven days of the week) and consider the
difference between the base set and one of its subsets. Once the base set has
been defined, we can also abbreviate the complement as $B^{C}$ or $\bar{B}$,
since it is clear which base set the complement refers to.

## Summary and outlook

| Operation | Symbol | Meaning | Logic |
| --------- | ------ | --------- | ----- |
| Intersection | $\cap$ | elements in $A$ **and** $B$ | $\land$ |
| Union | $\cup$ | elements in $A$ **or** $B$ | $\lor$ |
| Difference | $\setminus$ | elements in $A$, but not in $B$ | |
| Complement | $\bar{B}$, $B^C$ | all elements of the base set except $B$ | |

Now that we have learned how sets can be combined to form new sets using the
operations of intersection, union, and difference, in the next chapter we will
look at some very important sets, namely the natural numbers, the integers, the
rational numbers, and the real numbers.
