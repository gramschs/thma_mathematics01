# Sets

## Learning goals

```{admonition} Learning goals
:class: attention
* [ ] You understand the concept of a **set**.
* [ ] You are familiar with the technical term **element of a set**.
* [ ] You can represent and compare sets in different ways.
```

## What is a set?

In mathematics, a set is a collection of objects. These objects can be
mathematical objects such as numbers, geometric shapes, or functions. However,
we can also consider the books on a shelf or the days of the week as a set. It
is important that the objects are distinguishable and that we can decide for
each individual object whether it belongs to the set or not (see also [Wikipedia
→ Set](https://en.wikipedia.org/wiki/Set_(mathematics))).

Let's take the number of working days as an example. In Germany, working days
usually consist of

* Monday,
* Tuesday,
* Wednesday,
* Thursday, and
* Friday.

The days are distinguishable from one another; it definitely makes a difference
whether it is Monday or Friday. Furthermore, we can decide whether a day belongs
to the set of weekdays or not. Wednesday belongs to the set of weekdays, Sunday
does not belong to the set of weekdays. The objects that belong to the set are
called **elements of the set**.

```{note} What is ... a set?
In mathematics, a **set** is a collection of distinguishable objects for which
it can be clearly determined whether a particular object belongs to the set or
not. The objects belonging to the set are called **elements of the set**.
```

## How are sets represented?

In mathematics, there are three ways of representing sets:

1. Enumeration (Roster method),
2. Description (set-builder notation), and
3. graphical representation as a Venn diagram.

For the **enumeration**, sometimes called **Roster methode** we use the
so-called curly brackets `{` and `}` and write down the elements:

\begin{equation*}
W = \{\text{Monday}, \text{Tuesday}, \text{Wednesday}, \text{Thursday}, \text{Friday} \}.
\end{equation*}

The order of the elements is not important; we can also sort the elements
alphabetically, for example, and obtain the same set $W$:

\begin{equation*}
W = \{\text{Friday}, \text{Monday}, \text{Tuesday}, \text{Thursday}, \text{Wednesday}\}.
\end{equation*}

We use the symbol $\in$ to write that an element *belongs to the set*, i.e., is
part of it:

\begin{equation*}
\text{Monday} \in W.
\end{equation*}

In words: Monday belongs to the set of working days $W$.

If an object does not belong to the set, we use the symbol $\notin$. Sunday does
*not* belong to the set of working days, so

\begin{equation*}
\text{Sunday} \notin W.
\end{equation*}

A set can also be **empty** and contain no elements. For an empty set $S$, we
write

\begin{equation*}
S = \{\} \quad \text{ or } \quad S = \emptyset.
\end{equation*}

Let's look at a second example, namely the days of the month of April:

\begin{equation*}
A = \{1, 2, 3, 4, 5, \dots, 30\}.
\end{equation*}

Once the pattern is clear, bullet points `...` can also be set. The first half
of April, which we abbreviate as $A_1$, is then

\begin{equation*}
A_{1} = \{1, 2, 3, 4, \dots, 15\}.
\end{equation*}

The second way to enumerate a set is by means of a **description** or the
so-called **set-builder methode**. The first half of April consists of all days
in April that are before or equal to the 15th day. Mathematically, this is
written as follows:

\begin{equation*}
A_{1} = \{d\in A \;|\; d \leq 15\}.
\end{equation*}

So we say that the set $A_1$ consists of all days in April ($d\in A$) and then
use the symbol $|$ to require that these days in April must satisfy an
additional condition, namely $t\leq 15$. The symbol $|$ is read as "for which
the following applies". This allows us to describe the days $\{1, 2, 3, \ldots,
15\}$ instead of listing them.

In this example, the list is shorter and easier to understand than the
description. The descriptive representation is often more practical than the
list, especially for large or infinite sets.

Let's return to the example of working days to introduce the third type of
representation.

```{figure} pics/fig01_venn_diagram_working_days_EN.svg
---
width: 100%
name: fig01_venn_diagram_working_days_EN
---
Graphical representation of a set; the set is represented as an ellipse and
elements of the set are written inside the ellipse. Objects that do not belong
to the set are written outside the ellipse. (Source: own representation; license
[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

Graphical representations of sets are very common, especially when it comes to
calculating with sets, which we will learn about in the next chapter. We also
refer to the graphical representation as a **Venn diagram** (see [Wikipedia →
Venn diagram (https://en.wikipedia.org/wiki/Venn_diagram)). In a set diagram,
objects are placed inside geometric shapes such as circles or ellipses to
indicate that they are elements of the set. Objects that do not belong to the
set are placed outside.

We will also use Venn diagrams to clarify what the terms subset and superset
mean and when two sets are equal.

## Subset, superset, and equality of sets

Let's return to the example of working days. We abbreviate the set of working
days with $W_5$, i.e.

\begin{equation*}
W_5 = \{\text{Monday},\text{Tuesday},\text{Wednesday},\text{Thursday},\text{Friday}\}.
\end{equation*}

We abbreviate the set of all weekdays with $W_7$, i.e.

\begin{equation*}
W_7 = \{\text{Monday},\text{Tuesday},\text{Wednesday},\text{Thursday},\text{Friday},
\text{Saturday}, \text{Sunday}\}.
\end{equation*}

Every working day is also a weekday. Mathematically speaking, every element of
$W_5$ is also an element of the set $W_7$. We refer to the set of working days
$W_5$ as a **subset** of the weekdays $W_7$ and write:

\begin{equation*}
W_5 \subseteq W_7.
\end{equation*}

Conversely, we call the weekdays a **superset** of the working days and write
$W_7 \supseteq W_5$, i.e., with a mirror-inverted subset symbol. In a Venn
diagram, one geometric shape (here a circle for the working days) lies
completely within the other geometric shape (here an ellipse for the weekdays).

```{figure} pics/fig01_subset_as_venn_diagram_EN.svg
---
width: 100%
name: fig01_subset_as_venn_diagram_EN
---
Venn diagram showing the subset of working days $W_5$ and the superset of
weekdays $W_7$ with the relationship $W_5\subseteq W_7$ (Source: own
representation; license [CC BY-NC-SA
4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/))
```

Now one question remains: When are two sets equal? Two sets are equal if every
element of the first set is an element of the second set and, at the same time,
every element of the second set is also an element of the first set. Or, in
other words: the first set $S_1$ is a subset of the second set $S_2$ and $S_2$
is a subset of $S_1$. Mathematically, we write:

\begin{equation*}
S_1 = S_2, \quad \text{if} \quad S_1 \subseteq S_2 \; \text{\textbf{ and }} \;
S_2 \subseteq S_1.
\end{equation*}

For example, we can list the number of working days according to their occurrence

\begin{equation*}
W_1 = \{\text{Monday}, \text{Tuesday}, \text{Wednesday}, \text{Thursday}, \text{Friday} \}.
\end{equation*}

or alphabetically

\begin{equation*}
W_2 = \{\text{Friday}, \text{Monday}, \text{Tuesday}, \text{Thursday}, \text{Wednesday}\}.
\end{equation*}

Nevertheless, the two sets are equal because they contain the same elements and
the order of the set is irrelevant. So $W_1$ is a subset of $W_2$ and at the
same time $W_2$ is a subset of $W_1$, hence, $W_1 = W_2$.

Some textbooks introduce the term **proper subset**. In our example, the set of
weekdays $W_7$ has two elements (Saturday and Sunday) that do not belong to the
set of working days $W_5$. Thus, $W_5$ is a proper subset of $W_7$. If it is
important to express that $W_5$ is a proper subset of $W_7$, we can write $W_5
\subsetneq W_7$. In the following, we will point out when the difference is
important. Otherwise, we do not distinguish between proper subsets and subsets
and use the symbol $\subseteq$.

## Summary and outlook

In this chapter, we learned what sets are and how they are represented
mathematically. In the next chapter, we will learn how to perform calculations
with sets.
