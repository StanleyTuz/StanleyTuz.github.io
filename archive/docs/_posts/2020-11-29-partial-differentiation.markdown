---
layout: posts
title:  "Partial Differentiation"
date:   2020-11-29
categories: jekyll update
usemathjax: true
tags: calculus analysis partial differentiability differential jacobian
---

In this post, I am taking notes on the theory of multivariate, vector-valued differentiation as developed by Spivak in *Calculus on Manifolds* (1965). In particular, I focus on the relationship between partial derivatives and the derivative (AKA, the Jacobian matrix).

### Overview of the Development

<div class="definition">
The multivariable, vector-valued function $f:\mathbb{R}^n \rightarrow \mathbb{R}^m$ is called differentiable at $a\in \mathbb{R}^n$ if there exists a linear mapping $\lambda:\mathbb{R}^n \rightarrow \mathbb{R}^m$ so that $$ \lim_{h\rightarrow 0} \frac{\left|f\left(a+h\right) - f\left(a\right) - \lambda\left(h\right)\right|}{\left|h\right|}=0.$$ The linear mapping $\lambda$ is called the derivative of $f$ at $a$, often denoted $Df\left(a\right)$.
</div>

This definition of derivative, unlike the standard definition for single-variable function $f$, is more in line with the "linear approximation" interpretation of the derivative: as $h\rightarrow 0$, the numerator shrinks relative to $h$ so that $$ f\left(a+h\right) \approx f\left(a\right) + Df\left(a\right)\cdot h$$.

Note that since $\lambda$ is a linear mapping, it has a matrix representation so that its operation on vectors is via matrix-vector multiplication. This matrix representation is generally represented by the notation "$Df\left(a\right)$", where the matrix is with respect to the standard bases on $\mathbb{R}^n$ and $\mathbb{R}^m.$ With this in hand, we have $\lambda\left(h\right) = Df\left(a\right)\cdot h$ where $\cdot$ denotes standard matrix multiplication, which is how the matrix $Df\left(a\right)$ is commonly defined. It is called the *Jacobian matrix* of $f$ at $a$. An immediate goal of the development is to determine the precise form of this matrix, i.e., what its elements are.

### What are partial derivatives?

As we might recall from our early studies of the more computational aspects vector calculus, the elements of the Jacobian matrix are the partial derivatives of the various component functions of $f:\mathbb{R}^n\rightarrow \mathbb{R}^m$. To make this equivalence precise, we must develop first the theory of the partial derivatives of a multivariate function. A key initial result, easily proven via the triangle inequality and the definition of the derivative, is that a vector-valued function is differentiable if and only if its components all are. Note that a function $f:\mathbb{R}^n\rightarrow \mathbb{R}^m$ is comprised of $m$ scalar-valued, multivariate functions: \begin{equation} f\left(x\right) = \left[ 
    \begin{array}{l} 
        f^1\left(x\right) \\ 
        f^2\left(x\right) \\ 
        \ldots \\ 
        f^m\left(x\right) \\
    \end{array} 
    \right]^T \end{equation} where $f^i:\mathbb{R}^n\rightarrow \mathbb{R}$. Thus, a function of this sort merely collates the component functions into a vector.

<div class="lemma">
A function $f:\mathbb{R}^n \rightarrow \mathbb{R}^m$ is differentiable at $a\in \mathbb{R}^n$ if and only if each component function $f^i:\mathbb{R}^n\rightarrow \mathbb{R}$ is differentiable at $a$.
</div>
<div class="proof">
<p>Certainly, if $f$ is differentiable, then the component functions $f^{i} = \pi_i \circ f$ are also differentiable, thanks to the chain rule, and since the projections $\pi_i:\mathbb{R}^n\rightarrow \mathbb{R}$ are differentiable.
</p>
<p>
Conversely, assume each $f^i$ is differentiable at $a$. Then 
\begin{align}
\left|f\left(a+h\right) + f\left(a\right) - Df\left(a\right)\cdot h \right| & \leq \sum_{i=1}^n  \left|f^i\left(a+h\right) + f^i\left(a\right) - Df^i\left(a\right)\cdot h \right| 
\end{align}
where $Df^i\left(a\right)$ is the $i$-th row of the Jacobian matrix $Df\left(a\right)$. Dividing by $\left|h\right|$ and taking the limit $h\rightarrow 0$ proves the result.
</p>
</div>

This observation will allow us to simplify by restricting our attention to functions $f:\mathbb{R}^n\rightarrow \mathbb{R}$. These are functions which take in $n$ coordinates and return a single scalar (this is often done within proofs). The partial derivatives, which we now define, describe the sensitivity of this scalar output to changes in one of the input coordinates.

<div class="definition">
The $i$-th partial derivative of $f:\mathbb{R}^n\rightarrow \mathbb{R}$ at $a\in \mathbb{R}^n$ is the quantity $$ D_i f\left(a\right) = \lim_{h\rightarrow 0} \frac{f\left(a^1,a^2,\ldots,a^i+h,\ldots,a^n\right)-f\left(a^1,a^2,\ldots,a^i,\ldots,a^n\right)}{h} $$
</div>

Notice that this is the usual definition of the derivative of the scalar-valued, univariate function $g\left(x\right) = f\left(a^1,a^2,\ldots,x,\ldots,a^n\right)$. In the next section, we will see that, perhaps as expected, the derivative and the partial derivatives are intertwined.







### The Derivative vs Partial Derivatives

<div class="theorem">
Let $f:\mathbb{R}^n \rightarrow \mathbb{R}^m$ be differentiable at $a$. Then the partial derivatives $$ D_j f^i \left(a\right) $$ exist for all component functions $f^i$, $i=1,\ldots,m$ and variables $j=1,\ldots,n$. Further, the derivative has the expression $$ Df\left(a\right) = \left(D_j f^i\left(a\right)\right), $$ that is, the $m\times n$ matrix whose components are the partial derivatives.
</div>

Hence, if the function is differentiable, then the partial derivatives exist and comprise the components of the Jacobian matrix.

What about the converse?

<div class="theorem">
Let $f:\mathbb{R}^n\rightarrow \mathbb{R}^m$, and assume that the component function partial derivatives $D_jf^i\left(x\right)$ exist in an open neighborhood of $a$ and that each of these partial derivative functions is continuous at $a\in \mathbb{R}^n$. Then the derivative $Df\left(a\right)$ exists.
</div>

Interestingly, this theorem does not provide the form of the derivative, merely concludes that it exists. This latter theorem allows us to build a differentiable function up from component functions which are, themselves, partial-differentiable. The former theorem gives us partial derivatives of any differentiable, multivariate function.


Spivak singles out a special corollary:
<div class="theorem">
Let $g_i:\mathbb{R}^n\rightarrow \mathbb{R}$ be continuously differentiable at $a\in \mathbb{R}^n$ for $i=1,\ldots,m$, and let $f:\mathbb{R}^m \rightarrow \mathbb{R}$ be differentiable at $\left(g_1\left(a\right),\ldots,g_m\left(a\right)\right)$. Then define $F:\mathbb{R}^n\rightarrow \mathbb{R}$ as $$ F\left(x\right) = f\left(g_1\left(x\right),\ldots,g_m\left(x\right)\right).$$ Then $F$ we can find partial derivatives of $F$, which satisfy $$ D_iF\left(a\right) = \sum_{j=1}^m D_jf\left(g_1\left(a\right),\ldots,g_m\left(a\right)\right) \cdot D_ig_j\left(a\right) $$
</div>
How is this different from the standard chain rule? The function $F$ of interest looks very similar to the composition $f \circ g$ involved in the chain rule, but it is not the same (why?). Note that the proof uses both the previous theorem as well as the standard chain rule.

With this type of theorem in hand, once we are sure that our function in question satisfies the hypotheses, the problem of calculating partial derivatives is reduced from a limit definition proof to a simple mechanical calculation. Note that Spivak indicates that this theorem is "weaker" than the chain rule, and the use of this term indicates that the theorem either assumes more or concludes less than the chain rule.




{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}