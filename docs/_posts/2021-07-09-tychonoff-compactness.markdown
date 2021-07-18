---
layout: posts
title:  "Compactness and the Tychonoff Theorem"
date:   2021-07-09
categories: jekyll update
usemathjax: true
tags: compact topology space tychonoff
---
<p>
    The standard definition of topological compactness is in terms of open covers. There are several equivalent formulations, especially in the case of metric spaces. The Tychonoff theorem, which states that the arbitrary product of compact spaces is compact, can be easily proved using such an alternate formulation which involves intersections of closed subbases. To this end, we will discuss open and closed bases and subbases, the finite intersection property, how compactness can be defined, and the proof of the Tychonoff theorem.
</p>

### Bases, Subbases, and Covers
<p>
    Given a topological space $\left(X,\tau\right)$, a basis for this space is a collection of open sets $\mathcal{B}\subset \tau$ such that every open set can be written as a union of these basic sets. A closed basis is a collection of closed sets whose complements comprise an open basis.  
</p>
<p>
    An open subbasis for the topology is a collection of subsets of $X$ such that the class of all finite intersections of the subbasis elements is a basis for the topology. This subbasis generates the topology in the sense that the topology is the smallest one which contains the subbasis. A closed subbasis is a collection of subsets of $X$ whose complements comprise an open subbasis. As expected, finite unions of closed subbasis elements form a closed base, and this is pretty easily seen.
</p>
<p>
    Why bother with subbases? Subbasis elements need not be open or closed themselves: they are just any old subsets. They are useful in different contexts...
</p>
<p>
    We can go even further and define basic open covers of a space as open covers whose elements are drawn from a basis for the topology. As might be expected, open covers and basic open covers are quite intertwined. For example, we have the following:
</p>
<div class="lemma">
    A topological space is compact if and only if every basic open cover has a finite subcover.
</div>
<p>
    This obviously mirrors the standard definition of compactness in terms of open covers and subcovers, not necessarily basic.
</p>

### The Finite Intersection Property
<div class="definition">
    A class of subsets of a set has the finite intersection property is every finite subclass has non-empty intersection.
</div>
<p>
    The finite intersection property (FIP) may be possessed by a particular collection of subsets. In particular, it turns out that compactness of a topological space is strongly related to the closed subsets with the FIP:
</p>
<div class="theorem">
    Topological space $\left(X,\tau\right)$ is compact if and only if every class of closed sets $\left\{ C_i\right\}_{i\in I}$ with the FIP has non-empty total intersection: $$ \cap_{i\in I}C_i \neq \varnothing.$$
</div>
<p>
    In other words, a collection of sets with the FIP by definition have non-empty finite intersections; this theorem says that compact spaces are those for which we can take a collection of closed sets with FIP and extend the conclusion to the intersection of *all* the sets. The proof of this theorem hinges on the key that a class of closed subsets with empty intersection has complements which form an open cover of the space.
</p>

<p>
    The following theorem generalizes the previous two theorems in terms of subbases rather than just bases. The proof of this is quite long.
</p>
<div class="theorem">
    A topological space is compact if any subbasic open cover has a finite subcover. Equivalently, the space is compact if every class of *subbasic closed sets* with the FIP has non-empty intersection.
</div>

### The Tychonoff Theorem
<p>
    The Tychonoff theorem involves arbitrary non-trivial products of compact spaces:
</p>
<div class="theorem">
    The product $X = \Pi_i X_i$ of compact spaces $\left\{X_i\right\}$ is compact.
</div>
<p>
    We know that $X$ has the product topology on it, and we can start with the closed subbase which defines this topology. From the previous theorem, we can take a collection of subbasic closed sets, assume it has the FIP, and show that it has non-empty intersection. This requires moving to the factor spaces $X_i$, compact, and using the equivalent formulation of compactness in terms of the FIP.
</p>


### Conclusion
<p>

</p>


{% comment %}
<h3>References</h3>
{% bibliography --file refs --cited %}{% endcomment %}
