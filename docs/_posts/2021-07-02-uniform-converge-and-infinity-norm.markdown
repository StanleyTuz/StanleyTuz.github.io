---
layout: posts
title:  "Uniform Convergence and the Uniform Norm"
date:   2021-07-02
categories: jekyll update
usemathjax: true
tags: vector space basis matrix
---
<p>
    A question that struck me when learning about function spaces was regarding the relationship between uniform convergence of a function sequence and convergence in the uniform norm. In short, I discovered that I was getting tripped up by the difference between the loose introductory meaning of "convergence" of a function sequence and the strict notion of convergence in a function space.
</p>
<p>
    I will consider functions between arbitrary metric spaces $\left(X, d_X\right)$ and $\left(Y,d_Y\right)$. Let's define $$ F = \left\{ f:X\rightarrow Y \right\}$$ to be our space of functions, endowed with the usual vector space structure (corresponding to pointwise addition and scalar multiplication). In more interesting contexts, this space would have some more structure or at least some special properties, e.g., boundedness or continuity. Let $\left\{f_n\right\}_{n\in \mathbb{N}}$ be an arbitrary function sequence in this space.
</p>
<p>
    The general discussion of function sequence convergence often begins with defining *pointwise convergence*, where for any fixed point in the domain, $x \in X$, the sequence of points $\left\{ f_n\left(x\right) \right\}_{n \in \mathbb{N}} \subset Y$ converges. The limit is often written "$f\left(x\right)$", indicating that the collection of limiting points of the sequences $\left\{ \left(f_n\left(x\right)\right) \, \middle| \, x\in X\right\}$ themselves constitute a function. This resultant function $f$ is the "pointwise limit" of the $f_n$.
</p>
<p>
    The next step in the development is to compare pointwise convergence with *uniform convergence*, which is often described as pointwise convergence in which the same $\delta$ "works for all $x\in X$". This is the key to my confusion: this is what we are *defining* as convergence, but we have not yet mentioned any sort of metric on the space of function in which our function sequences live.
</p>
<p>
    The missing piece is exactly the uniform norm, $$ \left\lVert f \right\rVert_{\infty} := \sup_{x\in X} d_Y\left(f\left(x\right),0\right). $$
</p>



### Conclusion

<p>
    We will see similar ways of choosing bases to simplify matrix representations when we talk about eigenvalues of linear operators of finite-dimensional spaces.
</p>


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
