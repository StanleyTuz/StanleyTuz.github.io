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
<p>
    Given a surjective mapping $p:X\rightarrow Y$, a subset $C\subseteq X$ is said to be saturated with respect to $p$ if $C$ contains all fibers of $p$ which it intersects.
</p>

<p>
    Why do we care about saturated sets? The fact that they contain all fibers which intersect them ends up lending itself nicely to quotient spaces. If $p:X\rightarrow Y$ is any surjective map, then we can consider the equivalence relation on $X$ defined as $x \sim y$ if $p\left(x\right) = p\left(y\right)$, i.e., the domain is partitioned into subsets which take the same value under $p$. In this case, both $x$ and $y$ belong to the fiber $p^{-1}\left(\left\{x\right\}\right)$; this set is exactly the members of the equivalence class $\left[x\right]_{\sim}$. If $C\subset X$ is a saturated set containing $x$, then it contains the entire fiber $p^{-1}\left(\left\{x\right\}\right)$. Hence, if we think about the surjective map as inducing this equivalence relation on the domain, where the equivalence classes are exactly the fibers, the saturated sets do not "split" any fibers.
</p>
    
<p>
    We can take this further by reversing the above description. If we start with only a set $X$ and some equivalence relation on $X$, we can define the space of equivalence classes $X^*$ and the surjective map $p:X\rightarrow X^*$ sending a point to its equivalence class. In this way, we start only with the domain and an equivalence relation on it, and these induce the surjective map and codomain. To say that a subset $C\subseteq X$ is saturated with respect to the mapping $p$ means exactly what we described above: it contains all of the members of any equivalence class it intersects. In this case, the equivalence classes are specified at the outset --- the surjective map is induced by the equivalence relation.
</p>
<p>
    In summary, sets which are saturated with respect to a surjective map are well-behaved with respect to the associated equivalence relation.
</p>
<p>
    Another way to think about saturated sets is that they are exactly the preimage of a set in the codomain:
</p>
<div class="theorem">
    $C\subseteq X$ be saturated with respect to the surjective map $p:X\rightarrow Y$ if and only if $ C = f^{-1}\left(D\right)$ for some $D\subseteq Y$. 
</div>

### Example

<p>
    A basic example is the map $f:\mathbb{R}\rightarrow \mathbb{R}_{+}$ given by $$ f\left(x\right) = \left|x\right|. $$ This map is certainly surjective. The fiber of $f$ over any $y \in \mathbb{R}_+ $ is $$ f^{-1}\left(\left\{y\right\}\right) = \left\{ -y,y\right\}, $$ so the saturated sets in $X=\mathbb{R}$ are those which are symmetric about the origin. We can give $\mathbb{R}_+$ the quotient topology induced by the map $f$. The saturated open sets are unions of open intervals which are symmetric about the origin, and these map to open intervals in $\mathbb{R}_+$. Thus, these open intervals are open in the quotient topology on $\mathbb{R}_+$. Also, any interval in $\mathbb{R}$ containing the origin will map under $f$ to a closed-open interval in $\mathbb{R}_+$, so these are also open.
</p>
<p>
    To approach this same example from the other direction, take $X=\mathbb{R}$ and let $\sim$ be the equivalence relation consisting of points $\left\{-x, x\right\}$ for each $x \in X$. Take $p:X\rightarrow X^*$ as the map sending each $x\in X$ to its equivalence class. We can observe the same structure as before: the saturated sets are those which are symmetric about the origin. The difference now is that the codomain is no longer $\mathbb{R}_+$, but the space of equivalence classes, $X/\sim$. However, it seems like this space $X/\sim$ is closely related to $\mathbb{R}_+$. We can show that they are homeomorphic!
</p>
<p>
    Let $\phi: X/\sim \rightarrow \mathbb{R}_+$ be the map $$ \phi\left(\left[x\right]\right) = \left|x\right|. $$ We will show that this is well-defined and a homemorphism. To show that it is well-defined, we need to show that the function value is invariant under change of representative member of the equivalence class. Let $ y \in \left[x\right]$, so that $\left|x\right|=\left|y\right|$ by definition of the equivalence relation. Then $$ \phi\left(\left[x\right]\right) = \left|x\right| = \left|y\right| = \phi\left(\left[y\right]\right)$$ so the choice of representative member of the equivalence class does not change the function value: it is well-defined. 
</p>
<p>
    Next, let $U$ be open in $\mathbb{R}_+$. If $U$ is an open interval not containing $0$, then let $-U$ denote the open interval obtained by reflecting $U$ across the origin in $\mathbb{R}$. Then we have $$ \phi^{-1}\left(U\right)  = \left\{ \left[x\right] \, \middle| \, \left|x\right|\in U \right\}  = \left\{ \left[x\right] \, \middle| \, x \in -U\cup U \right\} $$ thus $p^{-1}\left(\phi^{-1}\left(U\right)\right) = -U \cup U$ which is open in $\mathbb{R}$, hence $\phi^{-1}\left(U\right)$ is open in $X/\sim$ in the quotient topology. Thus, $\phi$ is continuous. 
</p>
<p>
    Conversely, let $V\subseteq X/\sim$ be open. Then $p^{-1}\left(V\right)$ is open in $\mathbb{R}$. We know that this preimage is an open set in $\mathbb{R}$ which is symmetric about the origin; this is due to the nature of the equivalence classes we defined. Thus, $\phi\left(V\right)$ is exactly the non-negative "half" of this symmetric open set, itself an open set in $\mathbb{R}_+$ (we say "half" because it may contain the origin, resulting in a closed-open interval containing 0 in $\mathbb{R}_+$). Thus, $\phi^{-1}$ is continuous, and $\phi$ is a homeomorphism.
</p>
<p>
    In conclusion, we started this example with an equivalence relation, defined the quotient topology on the space of equivalence classes, and showed that this topological space is homeomorphic to the usual topology on $\mathbb{R}_+$. The homeomorphism we constructed is natural based on the relationship between the domain $\mathbb{R}$ and the equivalence relation, which identifies points equidistant from the origin. In the other approach, we could have started with the domain and the function $f\left(x\right) = \left|x\right|$ and directly constructed a quotient map from $\mathbb{R}$ to $\mathbb{R}_+$. A higher-dimensional version of this would be the map $f\left(x\right) = \left\lVert x \right\rVert_2$ in the plane.
<p>
<p>
    Note also that if the mapping $p:X\rightarrow X/\sim$ was a homeomorphism, then we would have shown that $\mathbb{R}$ is homeomorphic to $\mathbb{R}_+$ by composition of homeomorphisms. As expected, we did not. $p$ is not a homeomorphism, since it is not even injective.s
</p>






{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
