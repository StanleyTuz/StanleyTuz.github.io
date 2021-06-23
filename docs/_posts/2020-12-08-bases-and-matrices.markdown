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

<p>
    Similar to our discussion above, let $T:V^m \rightarrow W^m$ be a linear map. Let $\left(u_1,\ldots,u_p\right)$ be a basis for $\text{null}\left(T\right)$ and extend it to a basis $A=\left(v_1,\ldots,v_q,u_1,\ldots,u_p\right)$ of $V$. From above, we know that $\left(Tv_1,\ldots, Tv_q\right)$ is a basis --- not just a spanning set! --- for $\text{range}\left(T\right)\subseteq W$. Extend this latter set to a basis $B=\left(Tv_1,\ldots, Tv_q, w_1, \ldots, w_r\right)$ of $W$. Notice that these basis are intertwined with the map $T$, and were chosen based on the null set and range of $T$. What does the matrix representation of $T$ with respect to these bases look like?
</p>
<p>
    Recalling that each column of the matrix of $T$ with respect to bases $A$ and $B$, written here as $\left[ T \right]_{AB}$, is the image of a basis vector in $A$ under $T$, written in the basis $B$. Formally, the $j$-th column is $\left[Tv_j\right]_B$ (we know that this choice of structure of the matrix representation of $T$ leads to the isomorphism between matrices and finite-dimensional vector space linear mappings). Since the first $q$ vectors in the basis $A$ for $V$ are the basis for $\text{range}\left(A\right)$, by definition of $B$ we have $\left[Tv_j\right]_B = \left(0,0,\ldots,1, \ldots, 0\right)$ where the only non-zero entry is in the $j$-th place. Hence, the first $\dim \text{range}\left(T\right) = q$ columns of $\left[T\right]_{AB}$ have ones along the main "diagonal"; it's not a true diagonal unless $\dim V = \dim W$ and the matrix is square.
</p>
<p>
    The remaining $\dim \text{null}\left(T\right) = p$ vectors in $A$ are a basis for $text{null}\left(T\right)$, so we have $\left[Tu_i\right]_{B} = \left[0\right]_{B}= (0,\ldots,0\right)$ for the rest of the columns.
</p>


### Examples
<p>
    Consider the spaces $V=\mathbb{R}^3$ and $W=\mathbb{R}^2$ with the linear map $$ T\left(x,y,z\right) = \left(x+y, x+y\right).$$ By inspection, $\text{range}\left(T\right) = \text{span}\left(\left(1,1\right)\right)$, so the range has dimension 1. By the rank-nullity theorem, $\text{null}\left(T\right)$ must have dimension 2. Let's consider the matrix representation of $T$ with respect to a couple of bases.
</p>
<p>
    First, consider the standard Euclidean bases on both $V$ and $W$. The images of these vectors are trivial to compute and to write in the standard Euclidean bases, so the matrix representation is $$ \left[ \begin{array}{ccc} 1 & 1 & 0 \\ 1 & 1 & 0 \end{array} \right].$$
</p>
<p>
    More interestingly, let's follow the process above to get the simplified representation. The null space of $T$ is the set of all $\left(x,y\right)$ such that $x+y = 0$, i.e., $x=-y$, so the null space has basis $$\left( \left(1,-1,0\right), \left(0,0,1\right)\right)$$. The process for extending this to a basis of all of $V$ is to simply choose a vector which is not in the span of the previous vectors; by inspection, we come up with $$A=\left(\left( \begin{array}{c} 0 \\ 1 \\ 0 \end{array} \right), \left( \begin{array}{c}1\\ -1 \\ 0 \end{array} \right), \left( \begin{array}{c} 0 \\ 0 \\ 1 \end{array} \right)\right)) = \left(v_1, u_1, u_2\right)$$ as the desired basis for $V$, where we know $\left(Tv_1\right)$ is a basis for $\text{range}\left(T\right)$ and $\left(u_1,u_2\right)$ was constructed as a basis for $\text{null}\left(T\right)$. 
</p>
<p>
    The next step is to obtain the basis of $W$, $B$, corresponding to our choice of basis $A$ of $V$ which, together, admit the nice representation of $T$. As in our above discussion, we just push the $v_j$ through $T$, then extend the collection of these images to be a basis of $W$. Let $$ w_1 = \left(1, 0\right) = \left[Tv_1\right]_B = \left[\left(1,1\right)\right]_B $$. The remaining vectors in the basis $A$ are the null basis, so the corresponding columns are zeros. Thus, the matrix representation we have obtained is $$ \left[T\right]_{AB} = \left[ \begin{array}{ccc} 1 & 0 & 0 \\ 0 & 0 & 0 \end{array}\right] $$ which is precisely the representation we sought. 
</p>
<p>
    Let's quickly confirm this using an example. Consider $v=\left(1,2,3\right) \in \mathbb{R}^3$ in the standard basis. $T$ clearly maps this to $\left(3,3\right)\in \mathbb{R}^2$ in the standard basis. We want to verify that the matrix we have constructed exactly replicates this operation via matrix multiplication in the bases we found. We can by inspection write $v$ in the basis $A$ as $$ \left[v\right]_{A} = \left(\begin{array}{c} 3 \\ 1 \\ 3 \end{array}\right). $$ Performing the matrix multiplication gives us $$ \left[ T\right]_{AB}\left[v\right]_{A} = \left[\begin{array}{ccc} 1 & 0 & 0 \\ 0 & 0 & 0 \end{array}\right]\left[\begin{array}{c} 3 \\ 1 \\ 3 \end{array}\right] = \left[ \begin{array}{c} 3 \\ 0 \end{array}\right] $$ which is a vector in the basis $B$ on $W$. By rewriting this in the standard basis, we have $$ 3 \cdot \left( \begin{array}{c} 1 \\ 1 \end{array}\right) + 0 \cdot \left(\vdots\right)$$ which is exactly what we expected. Notice that we left the second basis vector of $W$ blank because we didn't ever actually compute it; we should have chosen it by extending the basis $\left(Tv_1\right)$ of $\text{range}\left(T\right)$ to all of $W$. It doesn't matter because these vectors will have a zero coefficient in the matrix of $T$, since they are not "reachable" by $T$, i.e., they are not in $\text{range}\left(T\right)$.
</p>



### Conclusion

We will see similar ways of choosing bases to simplify matrix representations when we talk about eigenvalues of linear operators of finite-dimensional spaces.


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}