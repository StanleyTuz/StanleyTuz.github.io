---
layout: posts
title:  "Vector Spaces: Linear Functions, Bases, and Matrices"
date:   2021-06-22
categories: jekyll update
usemathjax: true
tags: vector space basis matrix
---

In the spirit of trying to get more into advanced pure mathematics, I've taken a step back and started trying to re-learn linear algebra. One place I always used to trip at was the connection between vector spaces and matrices. In this post, I'm going to leave some notes pertaining to this connection which I've collected by studying the first few chapters of Axler's *Linear Algebra Done Right*.

<p>
To summarize, [a poster on Math StackExchange](https://math.stackexchange.com/a/1477478/592890) said it well:
>Think in terms of linear transformations, compute with matrices.

Several theorems in the book support this philosophy, specifically those which develop the isomorphism between the vector space of linear mappings between two vector spaces and the vector space of matrices.
</p>


### Linear Maps
<div class="definition">
    A map $T:V\rightarrow W$ between two linear spaces $V$ and $W$ (over $F$) is linear if $$ T\left(\alpha u + \beta v\right) = \alpha Tu + \beta Tv $$ for all $u,v \in V$ and $\alpha, \beta \in F$.
</div>
<p>
    Linear maps are just functions on vector spaces which have this particularly convenient property. Linear algebra as a subject is the study of linear spaces and the linear maps between them.
</p>


### Basis for a Linear Space

### Matrix Representations of Vectors

### Matrix Representations of Linear Maps

<div class="definition" >
    For a function $f:I\subset\mathbb{R}^1\rightarrow \mathbb{R}^1$ defined on an interval $I$ containing a point $x$, $f$ has derivative $$ f'\left(x\right) = \lim_{t\rightarrow x} = \frac{f\left(t\right)-f\left(x\right)}{t-x} $$ if the limit exists in $\mathbb{R}^1$.
</div>
<p>
    This is the standard $\epsilon-\delta$ definition of the derivative. By changing the variables $t = x+h$, where $h$ now represents a small distance from $x$, we have the equivalent expression $$ f'\left(x\right) = \lim_{h\rightarrow 0} = \frac{f\left(x+h\right)-f\left(h\right)}{h}. $$ The equivalence of these two is readily proved by appealing to the definition of limit.
</p>
<p>
    A second formulation of the derivative can be identified by making a small modification to the above: since $f'\left(a\right)$ is just a number, independent of the limit variable $h$, we can move it inside the limit with impunity, obtaining $$ \lim_{h\rightarrow 0} \frac{f\left(x+h\right) - f\left(x\right) - f'\left(a\right)\cdot h}{h} = 0 $$ Then the derivative can be defined as this number $f'\left(a\right)$ which makes this equation true, i.e., the difference quotient limiting to zero (we can show from the definition that derivatives are unique). It turns out that this expression most nicely generalizes to higher-dimensional Euclidean spaces.
</p>
<p>
    If we define the numerator of this latest expression to be $$ r\left(h\right) = f\left(x+h\right)-f\left(x\right)-f'\left(x\right)\cdot h,$$ then we can define the derivative as the (unique) number so that $$ f\left(x+h\right) = f\left(x\right) + f'\left(x\right)\cdot h + r\left(h\right), \; \text{where} \; \lim_{h\rightarrow 0} \frac{r\left(h\right)}{h} = 0. $$ Note that this is an exact equation; where $h$ is used in the $\epsilon-\delta$ difference quotient as the dummy limit variable, here it is an actual parameter which controls the point near $x$, $x'=x+h$, at which we want to find the function value. In fact, this definition of the derivative lends itself very nicely to the idea of the derivative as "the best linear approximation to $f$ at $x$." Rearranging the above, we have $$ f\left(x+h\right) - \left( f\left(x\right) + f'\left(a\right)\cdot h \right) = r\left(h\right)$$ so that the linear (in $h$) function $f\left(x\right) + f'\left(a\right)\cdot h$ approximates $f$ at $x+h$ with error $r\left(h\right)$. From the definition, this error in the approximation clearly tends to zero as $h$ does, emphasizing the fact that this approximation is only a local one; this makes sense, since the derivative is "local information."
</p>
<p>
    It is also common to see this last definition written as $$ f\left(x+h\right) = f\left(x\right) + f'\left(x\right)\cdot h + o\left(h\right) $$ where the "little-$o$" notation indicates a function of smaller order than $h$ as $h\rightarrow 0$, i.e., some function $r\left(h\right)$ so that $$ \lim_{h\rightarrow 0} \frac{r\left(h\right)}{h}=0$$ which is very clearly equivalent to the previous definition.
</p>


### The derivative in general Euclidean spaces
We consider the more general case of $f:E\subset\mathbb{R}^n \rightarrow \mathbb{R}^m$. The ideas of the difference quotient and linear approximation are the same, but now the domain and the range are vector spaces, and so division and multiplication must be treated more carefully.

<div class="definition" >
    For a function $f:E\subset\mathbb{R}^n\rightarrow \mathbb{R}^m$ defined on an open set $E$ containing a point $x$, $f$ has derivative $Df\left(x\right)$ if $$ \lim_{h\rightarrow 0} = \frac{\left|f\left(t+h\right)-f\left(x\right)-Df\left(h\right)\cdot h\right|}{\left|h\right|} = 0$$ where $Df\left(x\right):\mathbb{R}^n \rightarrow \mathbb{R}^m$ is a linear mapping.
</div>
<p>
    This is a clear generalization of the second definition of derivative we made above in the univariate, scalar-valued case. Note that vector magnitudes are taken in both the numerator and the denominator (though these norms are in different spaces). 
</p>
<p>
    We can obtain the familiar "linear approximation" representation if we make a similar definition: let $$ r\left(h\right) = f\left(x+h\right) - f\left(x\right) - Df\left(a\right)\cdot h. $$ Then the definition of the multivariate derivative is as the linear function $Df\left(a\right)$ so that $$ f\left(x+h\right) = f\left(x\right) + Df\left(a\right)\cdot h + r\left(h\right), \; \text{where} \; \lim_{h\rightarrow 0} \frac{\left|r\left(h\right)\right|}{\left|h\right|}. $$
</p>
<p>
    The linear function $Df\left(a\right)$, which is applied to perturbations $h$, is called the differential or derivative or total derivative of $f$ at $x$. Since it is a linear transformation, it admits a matrix representation, in particular in the standard Euclidean bases for $\mathbb{R}^n$ and $\mathbb{R}^m$. This matrix represesntation is called the Jacobian matrix.
</p>

{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}