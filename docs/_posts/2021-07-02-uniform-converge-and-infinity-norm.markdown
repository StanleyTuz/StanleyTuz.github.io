---
layout: posts
title:  "Uniform Convergence and the Uniform Norm"
date:   2021-07-02
categories: jekyll update
usemathjax: true
tags: vector space basis matrix
---
<p>
    A question that struck me when learning about function spaces was regarding the relationship between uniform convergence of a function sequence and convergence in the uniform norm.
</p>
<p>
    I will consider functions between arbitrary metric spaces $X$ and $Y$. The general discussion of function sequence convergence often begins with defining *pointwise convergence*, where for each
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
