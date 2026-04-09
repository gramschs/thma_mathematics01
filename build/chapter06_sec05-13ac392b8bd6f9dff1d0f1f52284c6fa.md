---
authors:
  - name: Simone Gramsch
---

# The Inverse Function Rule

In chapter 4 we constructed the inverse functions of the exponential and of the trigonometric functions by reflecting their graphs about the line $y = x$. We now ask a natural calculus question: if we know the derivative of a function, what can we say about the derivative of its inverse? The answer follows from the chain rule and gives us the derivatives of the logarithm and the inverse trigonometric functions in one unified step.

```{admonition} Learning goals
:class: attention
* [ ] You know the **inverse function rule**: if $f$ is differentiable and invertible near $x_0$, then
  \begin{equation*}
  \bigl(f^{-1}\bigr)'(y_0) = \frac{1}{f'\bigl(f^{-1}(y_0)\bigr)}.
  \end{equation*}
* [ ] You can use the inverse function rule to derive the derivatives of $\ln(x)$, $\arcsin(x)$, $\arccos(x)$, and $\arctan(x)$.
* [ ] You are familiar with the **inverse trigonometric functions** $\arcsin$, $\arccos$, and $\arctan$, their domains, and their ranges.
```
