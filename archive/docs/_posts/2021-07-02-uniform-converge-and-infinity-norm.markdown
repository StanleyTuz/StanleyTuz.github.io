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
    I will consider functions between arbitrary metric spaces $\left(X, d_X\right)$ and $\left(Y,d_Y\right)$. Let's define $$ F = \left\{ f:X\rightarrow Y \right\}$$ to be our space of functions, endowed with the usual vector space structure (corresponding to pointwise addition and scalar multiplication). In more interesting contexts, this space would have some more structure or at least some special properties, e.g., boundedness or continuity. Let $\left(f_n\right)_{n\in \mathbb{N}}$ be an arbitrary function sequence in this space.
</p>
<p>
    A quick note: we are concerned with convergence of sequences of functions. Thus, we use the definition of sequence convergence, which involves indexing through the natural numbers. The "closeness" in the domain, $X$, is less important: the epsilon-delta definitions come up when we discuss continuity of functions and function sequences.
</p>
<p>
    The general discussion of function sequence convergence often begins with defining *pointwise convergence*, where for any fixed point in the domain, $x \in X$, the sequence of points $\left(f_n\left(x\right) \right)_{n \in \mathbb{N} } \subset Y$ converges. The limit is often written "$f\left(x\right)$", indicating that the collection of limiting points of the sequences $\left\{ \left(f_n\left(x\right)\right)_{n\in\mathbb{N}} \, \middle| \, x\in X\right\}$ themselves constitute a function. This resultant function $f$ is the "pointwise limit" of the $f_n$, and we often write $$ f\left(x\right) := \lim_{n\rightarrow \infty} f_n\left(x\right), $$ as the definition. Note that the convergence of the function sequence is entirely defined by convergence at each individual point in the domain, and so for a given $\epsilon>0$, each $x\in X$ will generally have a different $n_0 \in \mathbb{N}$ which works.
</p>
<p>
    Pointwise convergence has some limitations. A primary one is that the pointwise limit of continuous functions need not be continuous. This is easily seen by the example...
</p>
<p>
    The next step in the development is to compare pointwise convergence with *uniform convergence*, which is often described as pointwise convergence in which the same $\delta$ "works for all $x\in X$". Formally, the $\left(f_n\right)_{n\in\mathbb{N}}$ converges to $f$ uniformly if for arbitrary $\epsilon>0$, there is some $n_0 \in \mathbb{N}$ so that $$ n > n_0 \implies d_Y\left(f_n\left(x\right), f\left(x\right)\right) < \epsilon $$ for *all* $x \in X$. Thus, the functions in the sequence get arbitrary close to the limiting function "all at once". The limit of uniformly convergent sequences has much nicer properties than the general pointwise counterparts.
</p>
<p>
    My confusion is how these notions of "convergence" are formally related to convergence in the space of functions. We are *calling* these function sequences convergent, but we have not yet mentioned any sort of metric on the space of function in which our function sequences live. The missing piece is exactly the uniform norm, $$ \left\lVert f \right\rVert_{\infty} := \sup_{x\in X} d_Y\left(f\left(x\right),0\right). $$ In the next section, I will show that sequence of functions is "uniformly convergent" if and only if it is convergent in the uniform norm on $F$.
</p>

### Short proof of equivalence
<div class="theorem">
    Function sequence $\left(f_n\right)_{n\in \mathbb{N}}$ converges uniformly to $f$ if and only if it converges to $f$ in the uniform norm.
</div>
<p>
    Let $\left(f_n\right)_{n\in\mathbb{N}}$ converge uniformly to $f$ in the function space $F$, and let $\epsilon >0$ be given. Then by definition of uniform convergence, there is some $n_0 \in \mathbb{N}$ so that $$ n > n_0 \implies d_Y\left(f_n\left(x\right), f\left(x\right) \right) < \frac{\epsilon}{2} $$ for all $x \in X$. Thus, the set $$ B =
    \left\{ d_Y\left(f_{n'}\left(x'\right), f\left(x'\right) \right)\, \middle| \, n' > n_0, x' \in X \right\} $$ is a subset of $\mathbb{R}$ which is bounded above by $\epsilon /2$. By completeness of $\mathbb{R}$, we have a supremum $\beta = \sup B$ so that $$ \beta \leq \frac{\epsilon}{2} < \epsilon. $$ Now, if we fix $n > n_0$, we have $$ \left\{ d_Y\left(f_n\left(x\right), f\left(x\right)\right) \, \middle| \, x \in X \right\} \subseteq B, $$ so this set is also bounded above by $\beta$. Thus, we have $$ n > n_0 \implies \left\lVert f_n - f\right\rVert_{\infty} = \sup_{x\in X} d_Y\left(f_n\left(x\right), f\left(x\right)\right) \leq \beta < \epsilon. $$ Hence, $\left(f_n\right)_{n\in\mathbb{N}}$ converges to $f$ in the uniform norm on $F$.
</p>
<p>
    In the other direction, let $\left(f_n\right)_{n\in\mathbb{N}}$ converge to $f$ in the uniform norm on $F$, and let $\epsilon >0$. Then we have an $n_0 \in \mathbb{N}$ so that for $n>n_0$ and for any $x\in X$, we have $$ d_Y\left(f_n\left(x\right),f\left(x\right)\right) \leq \sup_{x' \in X} d_Y\left(f_n\left(x'\right), f\left(x'\right)\right) = \left\lVert f_n-f \right\rVert_{\infty} < \epsilon. $$ Thus, our $n_0$ works for all $x\in X$ to show that $\left(f_n\right)$ converges uniformly to $f$.
</p>


### Completeness
<p>
    How does completeness and the concept of Cauchy sequences work here? As always, Cauchy sequences are ones which are "intrinsically convergent", in that we would expect them to converge, since the sequence points get arbitrarily close. The sticking point is that the point they converge to may not lie within the space under consideration. The classical example of a Cauchy sequence failing to converge is the sequence $\left\{1/n\right\}_{n\in \mathbb{N}}$ in $\left(0,1\right)\subset\mathbb{R}$; the sequence is certainly Cauchy, but its limit, 0, is not in the space. The spaces in which Cauchy sequences converge are labeled "complete". Note that completeness of a metric space depends, of course, on the metric. In short, Cauchy sequences always "converge" in the sense that the points get arbitrarily close, but the space itself may not be well-behaved enough to contain these limits.
</p>
<p>
    In the above exploration, we skirted this issue and discussed only the mechanics of convergence. Our proof assumed in both directions that the sequence in question converged to a limit within the original space, and we didn't need to address completeness. In fact, Cauchy sequences converge in the sense described in the theorem. However, in interesting examples of function spaces, it is not always evident that the limit function is still within the original space. In complete metric spaces, we can start with well-behaved --- i.e., Cauchy --- sequences and be sure that their limit lies within the set; this is the utility of complete metric spaces. To show that a space is complete, we often need to start with an arbitrary Cauchy sequence, provide its limit, and show that the limit is still within the space. Key (unproven here): sequences of Cauchy functions always "converge" in the uniform norm, but they may not converge to a limit in the space.
</p>
<p>
    For example, we can show that the set of bounded, real-valued functions on a metric space $X$ is complete. In this example, we start with a Cauchy sequence of functions. By Cauchy, we mean that the functions get arbitrarily close in the uniform metric. Next, we guess that the limit of this sequence is the pointwise limit of the functions at each point $x\in X$ (this "converges" in the basic pointwise sense). We proceed to use the Cauchy-ness of the sequence to show that the sequence does indeed converge to our proposed limit in the uniform norm. Last, we need to verify that this limit function is bounded, and so it is still in the original space. This shows that the space is complete.
</p>




### Conclusion
<p>
    In summary, Cauchy sequences "should" always converge. For Cauchy function sequences in the uniform norm, the same is true. We have shown that convergence in the uniform norm is the same as the standard "uniform convergence". In a complete metric function space, every Cauchy function space converges to a point in the space.
</p>


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
