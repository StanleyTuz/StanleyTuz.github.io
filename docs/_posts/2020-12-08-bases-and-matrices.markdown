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


### Matrix Representations of Vectors
Assume we have a vector space $V$ with basis $\beta_V = \left( v_1, v_2,\ldots,v_m\right)$, so that $\dim V = m$. The significance of a basis is that every vector $v \in V$ may be written uniquely as a linear combination of the basis vectors. When the basis set and its ordering are understood, we can write a vector in an arbitrary linear space as a column matrix whose elements are the scalar coefficients in the combination. In particular, the vector $$ v = \alpha_1 v_1 + \alpha_2 v_2 + \cdots + \alpha_m v_m $$ can be written as the vector $$ \left[ v\right]_{\beta} = \left(\begin{array}{c} \alpha_1 \\ \alpha_2 \\ \vdots \\ \alpha_m \end{array} \right) $$ where I'll use the notation $\left[\cdot \right]_{\beta}$ to indicate the matrix representation of the enclosed quantity with respect to the basis $\beta$.

This matrix representation of an arbitrary vector becomes useful due to the definition of matrix multiplication, and from this, the important fact that any linear map between two finite-dimensional vector spaces can be represented as a matrix-vector product. 

<div class="theorem" text="Span of Range">
    Let $T:V\rightarrow W$ be a linear map between finite-dimensional vector spaces $V$ and $W$, and let $\beta = \left(v_1,v_2,\ldots,v_m\right)$ be a basis for $V$. Then $\left(Tv_1, Tv_2, \ldots, Tv_m\right)$ spans $\text{range}\left(T\right)$; if linearly independent, it is a basis for $\text{range}\left(T\right)$.
</div>

<p>
    The proof is nearly evident based on the linearity of $T$ and the definition of basis: let $w\in \text{range}\left(T\right) \subseteq W$. Then $w = Tv $ for some $v\in V$, which has the basis expansion $v = \alpha_1 v_1 + \cdots + \alpha_m v_m$. Thus $$ w = t\left(\alpha_1 v_1 + \cdots + \alpha_m v_m\right) = \alpha_1 Tv_1 + \cdots + \alpha_m Tv_m, $$ thus these vectors span $\text{range}\left(T\right)$. If the set is linearly independent, it is a linearly independent spanning set, and so is a basis for $\text{range}\left(T\right)$.
</p>
<p>
    Note that we are *not* saying that $\left(Tv_1, \ldots, Tv_m\right)$ spans all of $W$; it makes sense that it only hits the range of $T$, i.e., the things in $W$ which are "reachable" via $T$.
</p>
<p>
    What if the set $\left(Tv_1, \ldots, Tv_m\right)$ is not linearly independent? It spans $\text{range}\left(T\right)$, so it can certainly be reduced to a basis of $\text{range}\left(T\right)$ by throwing out redundant vectors. In this case, we have $\dim \text{range}\left(T\right) < m = \dim V$. 
</p>
<p>
    One thing I always get confused on is: what does this say about the matrix representation of $T$ with respect to the given bases? Well, if we are given bases for both $V$ and $W$, the matrix representation of $T$ with respect to these bases is set in stone. The columns are the basis vectors in $V$ written in the basis of $W$. If we want a different representation for $T$, we need to look at changing the bases.
</p>

### Something similar

<p>
    In Axler's proof of the rank-nullity theorem, he constructs a basis for $\text{range}\left(T\right)$ in much the same way that we did in finding the spanning set in the previous lemma. Unlike that situation, though, where we started with a basis for all of $V$, he starts by taking a basis $\left(u_1,\ldots,u_p\right)$ of $\text{null}\left(T\right)$, extending it to a basis $\left(u_1,\ldots,u_p,v_1,\ldots,v_q\right)$ of $V$, and showing that $\left(Tv_1,\ldots,Tv_q\right)$ is a basis of $\text{range}\left(T\right)$. In this way, he starts with a particular type of basis on $V$, one which is segregated into a collection of null basis vectors and non-null basis vectors, and shows that the non-null collection maps to a basis for the range. In doing so, he avoids needing to worry about the redundant vectors I encountered above. The proof of this is very similar. 
</p>

<p>
    A very interesting result follows this theorem and is described in an exercise (?). It asks for the existence of a basis for $V$ and a basis for $W$ in which the matrix representation of $T$ has only ones along the "diagonal" of the first $\dim \text{range}\left(T\right)$ entries. I claim that the bases mentioned in the previous paragraph nearly suit this purpose. The only change to be made is that the basis for $\text{range}\left(T\right)$ must be extended to a basis of all of $W$. However, since none of the rest of $W$ can be attained by $Tv$ for any $v\in V$, the repective columns of the matrix representation of $T$ will be all zeros. Thus, the matrix representation is still a $\dim W \times \dim V$ matrix, as usual, but it has this particularly simple structure.
</p>
<p>
    This is one of the key insights we gain as we study linear algebra: any linear map can be represented by matrix multiplication on the appropriate column vector space, and we can understand the linear map itself by looking at its matrix representation. Further, choosing our bases wisely --- and often based on the map itself, as in this case --- we can get very simplistic representations.
</p>

### Examples






{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}