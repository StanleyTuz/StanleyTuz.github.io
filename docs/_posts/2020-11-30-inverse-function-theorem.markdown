---
layout: posts
title:  "The Inverse Function Theorem"
date:   2020-11-30
categories: jekyll update
usemathjax: true
tags: calculus analysis inverse theorem
---

In this post, I am taking notes on the theory of multivariate, vector-valued differentiation as developed by Spivak in *Calculus on Manifolds* (1965). In particular, I focus on Spivak's proof of the inverse function theorem.

### Give Intuition from One Dimension
Recall from our discussion on continuity that if $f'\left(a\right)>0$ and $f'$ is continous on some neighborhood of $a$ (that is, $f$ is continuously differentiable there) then we have $f'\left(x\right)>0$ for all $x$ in a neighborhood $V$ of $a$. This means that $f$ is strictly increasing on $V$, and so it is injective there. That, in turn, means that its inverse, $f^{-1}$, exists and is well-defined on $f\left(V\right)$.

If we picture this situation graphically, on $V$, $f$ has positive slope. We can try to look at $f^{-1}$ by flipping the graph $\left(x,f\left(x\right)\right)$ over the line $y=x$, or by looking at the $y$-axis. Recall that $f'\left(a\right)>0$ means that the slope of the tangent line to the graph of $f$, at $a$, is positive; in other words, we linearly approximate $f$ at $a$ by a line with positive slope. If we consider the graph of the inverse function, the same linear approximation holds at $f\left(a\right)$, but the slope is inverted. The statement of the inverse function theorem for univariate functions makes this precise:

<div class="theorem">
Let $f:\mathbb{R}\rightarrow\mathbb{R}$ be continuously differentiable on a neighborhood of $a$, and assume $f'\left(a\right)\neq 0$. Then $f^{-1}$ is differentiable at $f\left(a\right)$ with $$ \left(f^{-1}\right)'\left(f\left(a\right)\right) = 1/f'\left(a\right) $$
</div>
Note that the result is sometimes written as $$ \left(f^{-1}\right)'\left(b\right) = 1/f'\left(f^{-1}\left(b\right)\right) $$ where $b$ is taken to be a point in the range of $f$.
<div class="proof">
Assume $f'\left(a\right)>0$. By the above discussion, we know that $f$ is strictly increasing and thus injective on some neighborhood $V$ of $a$. To determine the derivative of $f^{-1}$ at $f\left(a\right)$, we look at the difference quotient 
\begin{equation}
\frac{f^{-1}\left(y\right) - f^{-1}\left(b\right)}{y-b}
\end{equation}
where we are taking $y = f\left(x\right)$ and $b = f\left(a\right)$, so the inverses are well-defined on $V$ since $f$ is injective. Since we are taking limits as $x\rightarrow a$ (and $y\rightarrow b$, by continuity of $f$), we can safely restrict our concern to this neighborhood $V$. Then substituting these values, we obtain
\begin{equation}
\frac{f^{-1}\left(y\right) - f^{-1}\left(b\right)}{y-b} = \frac{f^{-1}\left(f\left(x\right)\right) - f^{-1}\left(f\left(a\right)\right)}{f\left(x\right)-f\left(a\right)} = \frac{x-a}{f\left(x\right)-f\left(a\right)} 
\end{equation}
By properties of limits, then, the right-hand side tends to $1/f'\left(a\right)$ as $x\rightarrow a$, or, equivalently, as $y\rightarrow b$. Thus we have
\begin{equation}
\left(f^{-1}\right)'\left(f\left(a\right)\right) = \lim_{y\rightarrow f\left(a\right)} \frac{f^{-1}\left(y\right) - f^{-1}\left(f\left(a\right)\right)}{y-f\left(a\right)} = \frac{1}{f'\left(a\right)}
\end{equation}
</div>


### Set up the general problem



{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}