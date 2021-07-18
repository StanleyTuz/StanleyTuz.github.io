---
layout: posts
title:  "Quotient Spaces: Basic Concepts"
date:   2021-07-18
categories: jekyll update
usemathjax: true
tags: topology space quotient saturated fiber
---
<p>
    The introductory concept of a topological quotient space has confused me for a while. The development in Munkres makes use of saturated sets and, for some reason, it took a while for this 
</p>



### Saturated Sets
<div class="theorem">
    Let $p:X\rightarrow Y$ be a surjective map. If $C\subset X$ is saturated with respect to $p$, then $C$ contains all fibers of $p$ which it intersects.
</div>

<p>
    Quick proof?
</p>

<p>
    Why do we care about saturated sets? The fact that they contain all fibers which intersect them ends up lending itself nicely to quotient spaces. If $p:X\rightarrow Y$ is any surjective map, then we can consider the equivalence relation on $X$ defined as $x \sim y$ if $p\left(x\right) = p\left(y\right)$, i.e., the domain is partitioned into subsets which take the same value under $p$. In this case, both $x$ and $y$ belong to the fiber $p^{-1}\left(\left\{x\right\}\right)$; this set is exactly the members of the equivalence class $\left[x\right]_{\sim}$. If $C\subset X$ is a saturated set containing $x$, then it contains the entire fiber $p^{-1}\left(\left\{x\right\}\right)$. Hence, if we think about the surjective map as inducing this equivalence relation on the domain, where the equivalence classes are exactly the fibers, the saturated sets do not ``split'' any fibers.
</p>
    
<p>
    We can take this further by reversing the above description. If we start with only a set $X$ and some equivalence relation on $X$, we can define the space of equivalence classes $X^*$ and the surjective map $p:X\rightarrow X^*$ sending a point to its equivalence class. In this way, we start only with the domain and an equivalence relation on it, and these induce the surjective map and codomain. To say that a subset $C\subseteq X$ is saturated with respect to the mapping $p$ means exactly what we described above: it contains all of the members of any equivalence class it intersects. In this case, the equivalence classes are specified at the outset --- the surjective map is induced by the equivalence relation.
</p>
<p>
    In summary, sets which are saturated with respect to a surjective map are well-behaved with respect to the associated equivalence relation.
</p>


### Example

<p>
    A basic example is the map $f:\mathbb{R}\rightarrow \mathbb{R}_{+}$ given by $$ f\left(x\right) = \left|x\right|. $ This map is certainly surjective. The fiber of $f$ over any $y \in \mathbb{R}_+$ is $$ f^{-1}\left(\left\{y\right\}\right) = \left\{ -y,y\right\}, $$ so the saturated sets in $X=\mathbb{R}$ are those which are ``symmetric'' about the origin.
</p>







{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
